---
title: Worm Cocoon Behavior
category: scripts
---

---

# Worm Cocoon Behavior

This script defines the behavior of a "worm cocoon" entity in Noita. When the cocoon receives damage, it has a chance to spawn a worm and then destroy itself.

## Key Functions

### `spawn_worm(entity_id, pos_x, pos_y)`

*   **Purpose:** Spawns a worm entity at the given position and then destroys the original entity (the cocoon).
*   **Parameters:**
    *   `entity_id`: The ID of the entity to be destroyed (the cocoon).
    *   `pos_x`: The X-coordinate for the worm's spawn.
    *   `pos_y`: The Y-coordinate for the worm's spawn.
*   **Action:** Calls `EntityLoad` to create the worm and `EntityKill` to remove the cocoon.

### `damage_received(damage, desc, entity_who_caused, is_fatal)`

*   **Purpose:** Handles incoming damage to the cocoon entity.
*   **Parameters:**
    *   `damage`: The amount of damage received.
    *   `desc`: A description of the damage source.
    *   `entity_who_caused`: The ID of the entity that caused the damage.
    *   `is_fatal`: A boolean indicating if the damage is fatal.
*   **Logic:**
    *   Retrieves the current entity's ID and transform.
    *   Sets a random seed based on game frame and entity position/ID for deterministic randomness.
    *   If the damage is fatal OR there's a 10% chance (randomly determined), it calls `spawn_worm` to transform the cocoon into a worm.

## Core Mechanics

*   **Transformation Trigger:** The cocoon transforms into a worm when it takes fatal damage or, with a 10% probability, when it takes any damage.
*   **Worm Spawning:** The `spawn_worm` function is responsible for creating the worm entity using `EntityLoad`.
*   **Self-Destruction:** Upon successful worm spawning, the cocoon entity is destroyed using `EntityKill`.