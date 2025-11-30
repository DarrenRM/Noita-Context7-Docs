---
title: Enlightened Laser Dark Projectile Spawner
category: scripts
---

---

# Enlightened Laser Dark Projectile Spawner

This script defines the behavior for spawning multiple "enlightened_laser_darkbeam" projectiles. It's designed to be attached to a projectile entity that acts as a spawner.

## Key Attributes

*   **`speed`**: Controls the base speed of the spawned projectiles.
*   **`count`**: Determines how many "enlightened_laser_darkbeam" projectiles are spawned.
*   **`entity_id`**: Retrieves the unique identifier of the spawner projectile.
*   **`pos_x`, `pos_y`, `rot`**: Gets the current position and rotation of the spawner projectile.
*   **`vel_x`, `vel_y`**: Calculates the normalized velocity vector of the spawner projectile, which is then used to set the velocity of the spawned projectiles.

## Spawning Logic

The script iterates `count` times to spawn individual projectiles.

### Projectile Spawning Details

*   **`shoot_projectile_from_projectile`**: This function is used to create new projectile entities.
    *   **`entity_id`**: The ID of the spawner projectile.
    *   **`"data/entities/projectiles/enlightened_laser_darkbeam.xml"`**: The XML file defining the appearance and behavior of the spawned projectile.
    *   **`px + Random( -5, 5 )`, `py + Random( -5, 5 )`**: The spawned projectile's position, with a slight random offset from the spawner's position.
    *   **`vel_x`, `vel_y`**: The velocity applied to the spawned projectile, derived from the spawner's velocity.

## Sound Effect

*   **`GamePlaySound`**: Plays a specific sound effect associated with the launch of the dark laser. This is done once from the spawner to prevent duplicate sounds.
    *   **`"data/audio/Desktop/projectiles.bank"`**: The audio bank containing the sound.
    *   **`"projectiles/enlightened_laser/launch_dark"`**: The specific sound event name.
    *   **`pos_x`, `pos_y`**: The position where the sound is played.