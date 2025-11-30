---
title: Projectile Avoiding Arc
category: scripts
---

---

# Projectile Avoiding Arc

This script modifies the velocity of a projectile to make it "avoid" surfaces it might hit. It achieves this by performing raycasts in four cardinal directions and adjusting the projectile's velocity away from any detected surfaces.

## Key Attributes and Logic

### Raycasting and Surface Detection

*   **`raycast_distance`**: Defines the maximum distance for each raycast.
*   **`raycast_dirs`**: A table containing normalized vectors for the four cardinal directions (right, down, left, up).
*   **`RaytraceSurfacesAndLiquiform`**: This function is used to detect surfaces and liquiform materials within the specified raycast distance.
*   **`raycast_success`**: A boolean indicating if a surface was hit by the raycast.
*   **`r_x`, `r_y`**: The coordinates where the raycast hit a surface.

### Velocity Adjustment

*   **`strength`**: A multiplier that controls how strongly the projectile's velocity is adjusted.
*   The script calculates a velocity adjustment based on the distance from the projectile to the hit surface and the direction of the raycast.
*   The adjustment is applied in the opposite direction of the raycast, pushing the projectile away from the detected surface.
*   The formula used for adjustment is: `( raycast_distance ^ 2 - ( r_x - pos_x ) ^ 2 ) * rdir_x * strength` (and similarly for the y-component). This formula prioritizes adjustments for surfaces closer to the projectile.

### Velocity Component Modification

*   **`edit_component( entity_id, "VelocityComponent", ... )`**: This function targets the `VelocityComponent` of the projectile.
*   **`ComponentGetValueVector2( comp, "mVelocity")`**: Retrieves the current velocity vector of the projectile.
*   **`ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y)`**: Updates the projectile's velocity by adding the calculated avoidance velocity.

## How it Works

1.  The script gets the current entity ID and its position.
2.  It initializes `vel_x_new` and `vel_y_new` to zero, which will store the calculated avoidance velocity.
3.  It iterates through four predefined directions.
4.  For each direction, it performs a raycast using `RaytraceSurfacesAndLiquiform`.
5.  If a surface is detected (`raycast_success` is true):
    *   It calculates a velocity adjustment vector that pushes the projectile away from the detected surface. The closer the surface, the stronger the push.
    *   This adjustment is accumulated into `vel_x_new` and `vel_y_new`.
6.  Finally, it modifies the projectile's `VelocityComponent`, adding the accumulated avoidance velocity to its existing velocity. This results in the projectile attempting to steer away from nearby obstacles.