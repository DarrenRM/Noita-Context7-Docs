---
title: Sunbaby Air Effect Projectile
category: scripts
---

# Sunbaby Air Effect Projectile

This script defines the behavior for a projectile spawned by the "Sunbaby" entity, specifically for its air effect. It generates a lightning projectile with a random initial velocity.

## Key Attributes

*   **Projectile Type**: Shoots a `lightning.xml` projectile.
*   **Spawn Location**: Originates from the Sunbaby entity's current position (`x`, `y`).
*   **Velocity Calculation**:
    *   A random angle between 0 and 359 degrees is generated.
    *   This angle is used to calculate `vel_x` and `vel_y` components for a projectile with a fixed `length` of 6000 units.
    *   The `vel_y` is negated to ensure it's directed away from the entity.

## Script Logic

1.  **Initialization**:
    *   Retrieves the `entity_id` of the Sunbaby.
    *   Gets the Sunbaby's current `x` and `y` coordinates.
    *   Sets a random seed based on game frame, component ID, and entity position for deterministic randomness.

2.  **Projectile Spawning**:
    *   Calculates a random `angle`.
    *   Defines a `length` for the projectile's velocity.
    *   Computes the `vel_x` and `vel_y` components using trigonometry based on the random angle and length.
    *   Calls `shoot_projectile` to create the lightning projectile with the calculated velocity.