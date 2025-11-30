---
title: Blood Tentacle Projectile
category: entities
---

# Blood Tentacle Projectile

This document describes the `bloodtentacle_0.xml` entity, representing a projectile used by a blood tentacle in Noita.

## Sprite Component

The `SpriteComponent` defines the visual appearance of the projectile.

### Key Attributes:

*   **`image_file`**: `data/entities/projectiles/tentacle/bloodtentacle_0.png` - Specifies the texture file for the projectile's sprite.
*   **`offset_x`**: `0` - Horizontal offset of the sprite from the entity's origin.
*   **`offset_y`**: `4.5` - Vertical offset of the sprite from the entity's origin.
*   **`update_transform`**: `0` - Disables automatic sprite transformation based on entity movement.
*   **`update_transform_rotation`**: `0` - Disables automatic sprite rotation based on entity rotation.
*   **`z_index`**: `0.8` - Determines the rendering order of the sprite. Higher values are rendered on top.