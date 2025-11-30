---
title: Tiny Ghost Shoot (Nerfed)
category: scripts
---

---

# Tiny Ghost Shoot (Nerfed)

This script defines the behavior for a "nerfed" variant of the tiny ghost's projectile attack. It targets the nearest mortal enemy within a specified range, attempts to shoot a projectile, and introduces a random delay between shots.

## Key Attributes

*   **Targeting Range**: `range = 150` - The maximum distance at which the ghost will search for enemies.
*   **Projectile Speed**: `projectile_velocity = 400` - The speed at which the fired projectile travels.
*   **Accuracy Scatter**: `scatter = 0.3` - Controls the randomness in the projectile's trajectory, making it less accurate.

## Targeting Logic

The script iterates through entities within the `range` and identifies potential targets based on the following criteria:

*   Must have the `"mortal"` tag.
*   Must possess a `GenomeDataComponent`.
*   Must have a herd relation less than 40 (indicating they are not part of the same herd or are hostile).
*   Must not be the same entity as the shooter (player vs. player check).

## Line of Sight (LOS) Check

*   `RaytraceSurfacesAndLiquiform(pos_x, pos_y, enemy_x, enemy_y)`: Before firing, the script checks if there are any surfaces or liquids obstructing the line of sight between the ghost and the target. If an obstruction is found, the ghost will not shoot.

## Projectile Firing

*   **Direction Calculation**: The script calculates the vector towards the nearest valid enemy.
*   **Scatter Application**: A random rotation is applied to the direction vector based on the `scatter` value to introduce inaccuracy.
*   **Projectile Type**: `shoot_projectile( root_id, "data/entities/projectiles/deck/light_bullet.xml", ...)` - Fires a projectile defined by `data/entities/projectiles/deck/light_bullet.xml`.

## Firing Delay

*   `ComponentSetValue(comp_id, "execute_every_n_frame", 110 + Random(20))`: After firing, the script sets a random delay for the next shot, ranging from 110 to 130 frames. This prevents multiple tiny ghosts from firing simultaneously.