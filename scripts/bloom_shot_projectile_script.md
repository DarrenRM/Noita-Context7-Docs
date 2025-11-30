---
title: Bloom Shot Projectile Script
category: scripts
---

# Bloom Shot Projectile Script

This script defines the behavior for the "Bloom Shot" projectile in Noita. When fired, it spawns multiple projectiles that spread outwards in a blooming pattern.

## Key Attributes

*   **`shot( projectile_id )` Function:** This is the main function executed when the projectile is fired.
    *   It retrieves the current entity ID and its position.
    *   It calculates the spread and velocity for multiple projectiles.

## Projectile Spawning Logic

The script iterates a set number of times (`how_many`) to spawn individual projectiles.

### Parameters for Spawning

*   **`how_many`**: Determines the number of projectiles spawned. (Default: 8)
*   **`angle_inc`**: Controls the angular separation between spawned projectiles.
*   **`theta`**: The initial angle for projectile direction.
*   **`length`**: The base velocity magnitude for the spawned projectiles.

### `shoot_projectile` Function Calls

For each iteration, `shoot_projectile` is called with the following arguments:

*   **`entity_id`**: The ID of the entity firing the projectile.
*   **`"data/entities/projectiles/bloomshot.xml"`**: The XML file defining the appearance and base properties of the spawned projectile.
*   **`pos_x + vel_x * 0.05, pos_y + vel_y * 0.05`**: The spawn position, slightly offset from the origin based on the calculated velocity.
*   **`vel_x, vel_y`**: The calculated velocity components for the spawned projectile.
*   **`false`**: A boolean indicating whether the projectile should be affected by gravity (false means no gravity).