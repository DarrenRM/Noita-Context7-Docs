---
title: Projectile: Fly Downwards
category: scripts
---

# Projectile: Fly Downwards

This script modifies the velocity of a projectile to ensure it consistently moves downwards.

## Key Functionality

The primary purpose of this script is to override the projectile's existing velocity and set its vertical component to a value twice its current magnitude, while setting the horizontal component to zero.

### Velocity Modification

The script targets the `VelocityComponent` of the projectile.

*   **`edit_component`**: This function is used to modify an existing component.
*   **`VelocityComponent`**: The component responsible for managing the entity's velocity.
*   **`mVelocity`**: The vector representing the projectile's current velocity.

The script calculates the current velocity's magnitude and then reassigns `mVelocity` such that:

*   `vel_x` is set to `0`.
*   `vel_y` is set to `velocity * 2`.

This effectively makes the projectile fall straight down with increased speed.