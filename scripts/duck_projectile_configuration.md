---
title: Duck Projectile Configuration
category: scripts
---

---

# Duck Projectile Configuration

This script defines the behavior and visual properties of the "duck" projectile in Noita. It primarily focuses on adjusting the sprite's horizontal scaling based on its velocity.

## Key Components and Attributes

### SpriteComponent

This component manages the visual representation of the projectile.

*   **`special_scale_x`**: This attribute is dynamically adjusted to flip the sprite horizontally.
    *   Set to `1` if the projectile's horizontal velocity (`vel_x`) is positive (moving right).
    *   Set to `-1` if the projectile's horizontal velocity (`vel_x`) is negative (moving left).

### VelocityComponent

This component governs the projectile's movement. The script reads the `mVelocity` vector to determine the horizontal direction.

## Script Logic

The script first retrieves the `entity_id` of the projectile and then accesses its `SpriteComponent`. It then modifies the `VelocityComponent` to:

1.  Read the current `mVelocity` vector.
2.  Check the sign of the horizontal velocity (`vel_x`).
3.  Update the `special_scale_x` of the `SpriteComponent` accordingly to ensure the duck sprite faces the direction of movement.