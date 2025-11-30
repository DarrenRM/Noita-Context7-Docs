---
title: Death Ice Explosion
category: scripts
---

# Death Ice Explosion

This script defines the behavior for an entity that explodes into ice projectiles upon death.

## Core Functionality

The `death` function is triggered when the entity is destroyed. It spawns multiple ice projectiles in a circular pattern around the entity's position.

### Key Attributes

*   **`death_type_bit_field`**: (Parameter) Bitfield representing the type of damage that caused the death.
*   **`damage_message`**: (Parameter) A string message associated with the damage.
*   **`entity_thats_responsible`**: (Parameter) The entity that caused the death.
*   **`drop_items`**: (Parameter) A boolean indicating whether items should be dropped.
*   **`script_wait_frames( entity_id, 10 )`**: Ensures the explosion logic only runs every 10 frames to prevent excessive spawning.
*   **`how_many = 12`**: The number of ice projectiles to spawn.
*   **`angle_inc = ( 2 * 3.14159 ) / how_many`**: Calculates the angular increment for projectile distribution.
*   **`length = 100`**: The velocity magnitude for the spawned projectiles.
*   **`shoot_projectile( entity_id, "data/entities/projectiles/ice.xml", pos_x, pos_y, vel_x, vel_y )`**: Spawns an individual ice projectile.

## Projectile Details

The projectiles spawned are of type `data/entities/projectiles/ice.xml`.