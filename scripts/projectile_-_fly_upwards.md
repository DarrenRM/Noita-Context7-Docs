---
title: Projectile - Fly Upwards
category: scripts/
---

# Projectile - Fly Upwards

This script modifies a projectile's velocity to make it fly directly upwards.

## Key Components and Attributes

### VelocityComponent Modification

The core functionality is achieved by editing the `VelocityComponent` of the projectile entity.

*   **`mVelocity`**: This attribute is directly manipulated to set the projectile's velocity.

### Velocity Calculation and Application

The script calculates the current velocity magnitude and then reorients the velocity vector to point purely upwards.

*   **Velocity Magnitude**: The script calculates the current speed of the projectile using `math.sqrt( ( vel_y ) ^ 2 + ( vel_x ) ^ 2 )`.
*   **Upward Velocity**: The `vel_x` component is set to `0`, and the `vel_y` component is set to the negative of the calculated velocity magnitude (`0 - velocity * 2`). This effectively doubles the upward speed.