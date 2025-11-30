---
title: Disc Bullet Bigger Trajectory
category: scripts
---

# Disc Bullet Bigger Trajectory

This script modifies the trajectory of a projectile, specifically a "disc bullet," to curve towards its owner.

## Key Functionality

The primary goal of this script is to apply a directional velocity to the projectile based on its distance and direction from the entity that shot it.

### Trajectory Modification Logic

1.  **Get Projectile and Owner Information:**
    *   Retrieves the projectile's current entity ID and its transform (position).
    *   Identifies the `owner_id` (the entity that fired the projectile) from the `ProjectileComponent`.

2.  **Calculate Direction and Distance:**
    *   If an owner is found, it retrieves the owner's transform.
    *   Calculates the `dir` (direction) and `dist` (distance) between the projectile and its owner.

3.  **Apply Velocity Adjustment:**
    *   The projectile's existing velocity (`vel_x`, `vel_y`) is modified.
    *   A new velocity component is added, calculated using `math.cos(dir)` and `math.sin(dir)` multiplied by the `dist` and a scaling factor (0.33). This creates a curving effect towards the owner.
    *   The `VelocityComponent` of the projectile is updated with this new, adjusted velocity.

## Key Components and Attributes

*   **`ProjectileComponent`**: Essential for identifying the projectile and its owner (`mWhoShot`).
*   **`VelocityComponent`**: Manages the projectile's movement. The `mVelocity` attribute is directly modified.
*   **`EntityGetTransform`**: Used to get the position of entities.
*   **`ComponentGetValueVector2` / `ComponentSetValueVector2`**: Functions for reading and writing 2D vector values from components.
*   **`get_direction` / `get_distance`**: Utility functions (presumably from `utilities.lua`) for calculating direction and distance between two points.

## Example Usage (Conceptual)

This script would be attached to a projectile entity that has a `ProjectileComponent` and a `VelocityComponent`. When the projectile is spawned, this script runs, and if it has a valid owner, its path will curve back towards that owner.