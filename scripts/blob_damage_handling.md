---
title: Blob Damage Handling
category: scripts
---

# Blob Damage Handling

This script defines how a "blob" entity in Noita reacts when it receives damage. Its primary function is to spawn smaller "miniblob" entities when its health is reduced below certain thresholds.

## Key Functionality

### `damage_received( damage, desc, entity_who_caused, is_fatal )`

This function is called automatically by the game engine whenever the entity it's attached to takes damage.

*   **`damage`**: The amount of damage being applied.
*   **`desc`**: A string describing the damage source (e.g., "fire", "explosion").
*   **`entity_who_caused`**: The ID of the entity that inflicted the damage.
*   **`is_fatal`**: A boolean indicating if this damage instance will kill the entity.

### Core Logic

1.  **Self-Damage Prevention**: The script checks if the damage was caused by the entity itself. If so, it returns immediately to prevent unintended behavior.
2.  **Herd Identification**: It retrieves a `herd_id` from the `GenomeDataComponent`. This might be used for grouping or identifying related entities, though it's not directly used in the damage response logic here.
3.  **Jump Velocity Modification**: The `ControlsComponent`'s `mJumpVelocity` is randomly altered. This causes the blob to jump erratically when damaged.
4.  **Health Tracking**: It reads the current `hp` and `max_hp` from the `DamageModelComponent`.
5.  **Minion Spawning Thresholds**:
    *   It calculates `minion_interval`, which is the health difference between spawning new miniblob entities. This is determined by dividing `max_health` by a fixed `minion_count` (set to 4).
    *   It then determines `nearest_interval`, which represents the health threshold at which the next miniblob should spawn. This is calculated based on the current health and the `minion_interval`.
6.  **Miniblob Generation**:
    *   A `while` loop iterates as long as the `new_health` (health after taking damage) is below the `nearest_interval` threshold, and a `limit` (set to 7) on the number of spawned minions is not reached.
    *   Inside the loop:
        *   A "duplicate" sound effect is played.
        *   The blob's position is slightly randomized.
        *   A new miniblob entity (`data/entities/animals/miniblob.xml`) is loaded at the randomized position.
        *   The `nearest_interval` is reduced by `minion_interval` to set the threshold for the *next* miniblob.
        *   The `count` of spawned minions is incremented.

## Key Components and Attributes

*   **`GenomeDataComponent`**:
    *   `herd_id`: Used to identify groups of entities.
*   **`ControlsComponent`**:
    *   `mJumpVelocity`: A `Vector2` value that controls the entity's jump force and direction. This is modified to create erratic jumps.
*   **`DamageModelComponent`**:
    *   `hp`: The current health points of the entity.
    *   `max_hp`: The maximum health points of the entity.

## Example Usage (Conceptual)

When a blob with 100 max HP takes damage:

*   `minion_count` = 4
*   `minion_interval` = 100 / 4 = 25

If the blob's current health is 80:

*   `nearest_interval` = `math.floor(80 / 25) * 25` = `3 * 25` = 75.
*   If damage reduces health to 70 (`new_health` < 75), a miniblob spawns.
*   `nearest_interval` becomes 75 - 25 = 50.
*   If health is further reduced to 40 (`new_health` < 50), another miniblob spawns.
*   `nearest_interval` becomes 50 - 25 = 25.
*   If health is further reduced to 10 (`new_health` < 25), another miniblob spawns.
*   `nearest_interval` becomes 25 - 25 = 0.
*   If health is further reduced to -10 (`new_health` < 0), another miniblob spawns.

This continues until the health drops below the calculated `nearest_interval` or the `limit` of 7 minions is reached.