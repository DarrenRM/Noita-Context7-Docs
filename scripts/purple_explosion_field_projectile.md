---
title: Purple Explosion Field Projectile
category: scripts
---

# Purple Explosion Field Projectile

This script defines the behavior of a projectile that creates a "purple explosion field." It primarily focuses on determining the location of the explosion and potentially targeting a nearby enemy.

## Key Attributes

*   **Area of Effect:** The `area` variable (set to `70`) defines the radius within which the script searches for potential targets.
*   **Targeting Logic:**
    *   The script checks for entities with the `"homing_target"` tag within the specified `area`.
    *   If enemies are found, there's a `1 in 5` chance (`Random(1, 5) == 2`) that the explosion will be centered on one of the found enemies.
    *   If no enemies are found or the targeting roll fails, the explosion's position is randomized within the `area` around the projectile's original location.
*   **Projectile Creation:** The core action is `shoot_projectile_from_projectile`, which spawns a new projectile (`"data/entities/projectiles/deck/purple_explosion.xml"`) at the determined `pos_x` and `pos_y`.

## Script Logic Breakdown

1.  **Initialization:**
    *   Retrieves the current projectile's entity ID and its transform (position).
    *   Sets the `area` for target detection.
    *   Finds all entities with the `"homing_target"` tag within the `area`.
2.  **Position Determination:**
    *   A random seed is set based on game frame and entity position for more varied results.
    *   If enemies are present and the random targeting condition is met:
        *   A random enemy from the found list is selected.
        *   The explosion's position (`pos_x`, `pos_y`) is set to the selected enemy's position.
    *   Otherwise (no enemies or targeting failed):
        *   The explosion's position is randomized within the `area` around the projectile's original location.
3.  **Explosion Spawning:**
    *   The `shoot_projectile_from_projectile` function is called to create the actual "purple explosion" projectile at the calculated position.