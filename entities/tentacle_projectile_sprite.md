---
title: Tentacle Projectile Sprite
category: entities
---

# Tentacle Projectile Sprite

This document describes the sprite component for the "tentacle_1" projectile entity in Noita.

## SpriteComponent

The `SpriteComponent` defines the visual appearance of the projectile.

### Key Attributes:

*   **`image_file`**: Specifies the texture file used for the sprite.
    *   Value: `data/entities/projectiles/tentacle/tentacle_1.png`
*   **`offset_x`**: The horizontal offset of the sprite from the entity's origin.
    *   Value: `0`
*   **`offset_y`**: The vertical offset of the sprite from the entity's origin.
    *   Value: `4.5`
*   **`update_transform`**: Determines if the sprite's transform (position, scale, rotation) should be updated based on the entity's transform.
    *   Value: `0` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated based on the entity's rotation.
    *   Value: `0` (Disabled)