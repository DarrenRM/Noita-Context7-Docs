---
title: Tongue 4 Projectile Sprite
category: entities
---

# Tongue 4 Projectile Sprite

This document describes the sprite component for the "tongue_4" projectile entity in Noita.

## SpriteComponent

This component defines the visual appearance of the projectile.

### Key Attributes:

*   **`image_file`**: Specifies the texture file used for the sprite.
    *   Value: `"data/entities/projectiles/tentacle/tongue_4.png"`
*   **`offset_x`**: Horizontal offset of the sprite from the entity's origin.
    *   Value: `"0"`
*   **`offset_y`**: Vertical offset of the sprite from the entity's origin.
    *   Value: `"4.5"`
*   **`update_transform`**: Determines if the sprite's transform (position, scale, rotation) should be updated automatically.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated automatically.
    *   Value: `"0"` (Disabled)
*   **`z_index`**: Controls the rendering order of the sprite. Higher values are rendered on top.
    *   Value: `"0.83"`