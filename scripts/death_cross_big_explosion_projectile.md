---
title: Death Cross Big Explosion Projectile
category: scripts
---

# Death Cross Big Explosion Projectile

This script defines the behavior for a projectile that creates a large, cross-shaped explosion of smaller projectiles.

## Core Functionality

The primary purpose of this script is to spawn multiple instances of `death_cross_big_laser.xml` projectiles in a radial pattern around the originating entity.

## Key Attributes

*   **`how_many`**: Determines the number of primary directions the explosion will spread in.
*   **`angle_inc`**: Controls the angular separation between these primary directions.
*   **`length`**: A base multiplier for the velocity of the spawned projectiles.
*   **`length_base`**: An additional offset to the velocity magnitude.
*   **`GamePlaySound`**: Triggers an explosion sound effect at the projectile's origin.

## Projectile Spawning Logic

The script uses nested loops to spawn projectiles:

1.  **Outer loop (`i`)**: Iterates through the primary directions defined by `how_many`.
2.  **Inner loop (`j`)**: Spawns multiple projectiles within each primary direction, with increasing velocity magnitudes.

### `shoot_projectile` Parameters

The `shoot_projectile` function is called to create each individual laser projectile. The key parameters are:

*   **`entity_id`**: The ID of the entity that fired this projectile.
*   **`"data/entities/projectiles/deck/death_cross_big_laser.xml"`**: The XML file defining the appearance and behavior of the spawned projectiles.
*   **`pos_x`, `pos_y`**: The origin coordinates for the spawned projectiles.
*   **`vel_x`, `vel_y`**: The calculated velocity components for each spawned projectile, determining its direction and speed.

### Velocity Calculation

The velocity of each spawned projectile is calculated using trigonometry:

```lua
local vel_x = math.cos( theta ) * (length * j + length_base)
local vel_y = math.sin( theta ) * (length * j + length_base)
```

Where:
*   `theta` is the current angle in radians.
*   `length * j + length_base` determines the magnitude of the velocity.

The `theta` is incremented by `angle_inc` in each iteration of the outer loop, creating the radial spread.