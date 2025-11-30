---
title: Air Essence Projectile Spawner
category: scripts
---

---

# Air Essence Projectile Spawner

This script defines the behavior for an "Air Essence" entity, specifically its projectile spawning mechanism. When an Air Essence is activated, it fires a burst of "air_bullet" projectiles in a circular pattern around its parent entity.

## Key Functionality

*   **Projectile Spawning:** The core function is to spawn multiple projectiles (`air_bullet.xml`) originating from the Air Essence's position.
*   **Circular Pattern:** Projectiles are fired at evenly distributed angles around the parent entity.
*   **Randomization:** The initial angle of the projectile spread is randomized for variation.

## Configuration

The following parameters can be adjusted to modify the projectile behavior:

| Parameter   | Description                                                              | Default Value |
| :---------- | :----------------------------------------------------------------------- | :------------ |
| `how_many`  | The number of projectiles to spawn.                                      | `16`          |
| `angle_inc` | The angular increment between each projectile (calculated automatically).  | N/A           |
| `length`    | The velocity magnitude (speed) of the spawned projectiles.               | `300`         |

## Script Logic

1.  **Initialization:**
    *   Retrieves the `entity_id` and its transform (`pos_x`, `pos_y`).
    *   Sets a random seed based on the entity's position for varied outcomes.
2.  **Angle Calculation:**
    *   Calculates the angular increment (`angle_inc`) to distribute projectiles evenly in a 360-degree circle.
    *   Sets an initial random angle (`theta`) for the first projectile.
3.  **Parent Check:**
    *   Ensures the Air Essence has a `parent_id` before proceeding. This prevents errors if the essence is not attached to another entity.
4.  **Projectile Firing Loop:**
    *   Iterates `how_many` times to spawn each projectile.
    *   Calculates the `vel_x` and `vel_y` components for the projectile's velocity based on the current `theta` and `length`.
    *   Updates `theta` for the next projectile.
    *   Calls `shoot_projectile` to create the `air_bullet.xml` entity with the calculated velocity.