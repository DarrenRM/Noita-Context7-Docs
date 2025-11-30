---
title: Vertical Wall Projectile Spawner
category: scripts
---

# Vertical Wall Projectile Spawner

This script defines the behavior for a projectile that spawns vertical wall segments. When this projectile is active, it creates a series of wall pieces and associated entities to construct a vertical barrier.

## Key Functionality

This script's primary purpose is to act as a spawner for wall-building projectiles. It doesn't have complex physics or damage properties itself, but rather orchestrates the creation of other entities.

### Projectile Spawning

The script utilizes `shoot_projectile_from_projectile` to spawn other entities.

*   **`shoot_projectile_from_projectile( entity_id, projectile_xml_path, pos_x, pos_y, vel_x, vel_y )`**: This function is called multiple times to create the wall components.

    *   **`entity_id`**: The ID of the current projectile entity.
    *   **`projectile_xml_path`**: The path to the XML file defining the projectile to be spawned.
    *   **`pos_x`, `pos_y`**: The position where the new projectile will be spawned.
    *   **`vel_x`, `vel_y`**: The velocity of the new projectile.

### Spawned Entities

The following entities are spawned by this script:

*   **`data/entities/projectiles/deck/wall_piece.xml`**: This is likely the visual component of the wall segment. It's spawned with no initial velocity.
*   **`data/entities/projectiles/deck/wall_builder.xml`**: This entity is spawned twice, with opposing vertical velocities (`vel_y` and `-vel_y`). This suggests it's responsible for the actual construction or placement of the wall segments, and the opposing velocities might be to ensure coverage or create a specific spawning pattern.
*   **`data/entities/projectiles/deck/wall_sound.xml`**: This entity is loaded to play a sound effect associated with the wall construction.

### Sound Effect

*   **`GamePlaySound( "data/audio/Desktop/projectiles.bank", "player_projectiles/bullet_laser/create", pos_x, pos_y )`**: Plays a sound effect upon the projectile's creation.

## Key Attributes/Elements

*   **`vel_y = 500`**: Defines the base vertical velocity for spawned projectiles.
*   **`shoot_projectile_from_projectile(...)`**: The core function for spawning other entities.
*   **`EntityLoad(...)`**: Used to load and activate the sound effect entity.
*   **`data/entities/projectiles/deck/wall_piece.xml`**: The entity representing a single wall segment.
*   **`data/entities/projectiles/deck/wall_builder.xml`**: The entity responsible for the wall construction logic.