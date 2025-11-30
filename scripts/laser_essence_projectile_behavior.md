---
title: Laser Essence Projectile Behavior
category: scripts
---

---

# Laser Essence Projectile Behavior

This script defines the behavior for a "Laser Essence" entity, specifically how it spawns and fires projectile bullets.

## Core Functionality

The primary purpose of this script is to spawn multiple projectile entities in a circular pattern around the essence.

### Key Attributes

*   **`how_many`**: Determines the number of projectiles to spawn. In this case, it's set to `8`.
*   **`angle_inc`**: Calculates the angular separation between each projectile, ensuring an even distribution in a circle.
*   **`theta`**: Initializes the starting angle for the first projectile, randomized between 1 and 360 degrees.
*   **`length`**: Defines the velocity magnitude (speed) of the spawned projectiles. Set to `300`.
*   **`parent_id`**: Retrieves the ID of the parent entity. Projectiles are fired from the parent's position.
*   **`shoot_projectile`**: A utility function (presumably from `utilities.lua`) used to spawn a projectile. It takes the parent entity ID, the projectile's XML definition, its spawn position, and its velocity components (`vel_x`, `vel_y`).

## Projectile Spawning Logic

The script iterates `how_many` times to spawn each projectile.

### Spawning Loop

1.  **Calculate Velocity**: For each iteration, `vel_x` and `vel_y` are calculated using trigonometry (`math.cos` and `math.sin`) based on the current `theta` and `length`. This creates projectiles moving in different directions.
2.  **Update Angle**: `theta` is incremented by `angle_inc` for the next projectile, ensuring a circular spread.
3.  **Spawn Projectile**: The `shoot_projectile` function is called with the calculated velocity and the projectile's XML definition (`data/entities/misc/essences/laser_bullet.xml`).

## Dependencies

*   `dofile_once("data/scripts/lib/utilities.lua")`: This line ensures that the `utilities.lua` script, which likely contains the `shoot_projectile` function, is loaded and executed.

## Notes

*   The script checks if `parent_id` is not `NULL_ENTITY` before proceeding, ensuring it only fires if it has a valid parent.
*   The `SetRandomSeed( pos_x, pos_y )` call ensures that the random angle generation is consistent for the same essence position across different game loads.