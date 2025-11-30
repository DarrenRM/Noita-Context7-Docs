---
title: Ghost Crystal Death Behavior
category: scripts
---

# Ghost Crystal Death Behavior

This script defines the behavior of a "Ghost Crystal" when it dies. Upon death, it spawns a ring of ice projectiles and logs a player kill if the responsible entity is a ghost.

## Key Functions

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This function is called when the entity associated with this script is destroyed.

*   **`damage_type_bit_field`**: Bitfield representing the type of damage taken.
*   **`damage_message`**: String message describing the damage.
*   **`entity_thats_responsible`**: The entity that caused the death.
*   **`drop_items`**: Boolean indicating if items should be dropped.

## Core Logic

### Projectile Spawning

*   The script waits for 10 frames before executing to prevent excessive spawning.
*   It spawns **12 ice projectiles** in a circular pattern around the entity.
*   Each projectile is an instance of `data/entities/projectiles/ice.xml`.

### Player Kill Logging

*   The script checks for a `VariableStorageComponent` with the key `"ghost_id"`.
*   If found, it retrieves the `ghost_id` and logs a player kill using `StatsLogPlayerKill( ghost_id )`. This suggests the entity might be a ghost that is targeting a player.