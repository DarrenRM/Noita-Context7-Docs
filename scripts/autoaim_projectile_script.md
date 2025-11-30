---
title: Autoaim Projectile Script
category: scripts/
---

# Autoaim Projectile Script

This script enables projectiles to automatically steer towards the nearest valid enemy within a specified range, provided there is a clear line of sight.

## Key Attributes

*   **`range`**: The maximum distance (in pixels) the projectile will search for a target.
*   **`steering_strength`**: Controls how strongly the projectile's velocity vector is adjusted to align with the target's direction. A value of `1.0` means it will instantly point towards the target, while `0.0` means no steering occurs.
*   **`scatter`**: Introduces a random deviation (in radians) to the projectile's final velocity direction, making its aim less precise.

## Functionality Breakdown

### Target Acquisition

1.  **Entity Identification**: The script first identifies the projectile's own entity ID and its current position.
2.  **Shooter Identification**: It retrieves the `ProjectileComponent` to determine which entity shot the projectile, preventing self-targeting.
3.  **Nearest Enemy Search**:
    *   Iterates through all entities within the `range` that have the `"mortal"` tag.
    *   Filters targets to ensure they have a `GenomeDataComponent` and are not part of the shooter's herd (relation < 70).
    *   Calculates the distance to each valid enemy and selects the closest one.

### Line of Sight (LOS) Check

*   If a valid enemy is found, a `RaytraceSurfacesAndLiquiform` check is performed from the projectile's position to the enemy's position. If the ray hits any surfaces or liquids, the target is ignored, and the script returns.

### Velocity Adjustment

1.  **Direction Calculation**: If LOS is clear, a normalized direction vector from the projectile to the enemy is calculated.
2.  **Current Velocity Retrieval**: The projectile's current velocity vector and speed are obtained.
3.  **Steering**:
    *   The current velocity direction is normalized.
    *   The `lerp` function is used to blend the current velocity direction with the calculated target direction, based on `steering_strength`.
    *   The resulting steered direction is normalized.
    *   The original speed is reapplied to the steered velocity vector.
4.  **Scatter Application**: A random angle within the `scatter` range is applied to the final velocity vector using `vec_rotate`.
5.  **Velocity Update**: The projectile's `VelocityComponent` is updated with the newly calculated and steered velocity.

### Visual Effects

*   If the script successfully finds a target and applies autoaim, it enables components tagged with `"autoaim_fx"` on the projectile entity.

```lua
-- Example of how steering_strength affects aim
-- steering_strength = 0.1 -- Projectile will barely turn towards the target
-- steering_strength = 0.8 -- Projectile will significantly turn towards the target
-- steering_strength = 1.0 -- Projectile will instantly point at the target (if LOS allows)

-- Example of how scatter affects aim
-- scatter = 0.0 -- Projectile will always fly perfectly straight towards the target (after steering)
-- scatter = 0.5 -- Projectile's final direction will have a noticeable random deviation
```