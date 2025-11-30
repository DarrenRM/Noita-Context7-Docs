---
title: Tongue 2 Projectile Sprite
category: entities
---

# Tongue 2 Projectile Sprite

This document describes the sprite component for the "Tongue 2" projectile entity in Noita.

## SpriteComponent

This component defines the visual appearance and basic positioning of the projectile.

### Key Attributes:

*   **`image_file`**: Specifies the texture file used for the sprite.
    *   Value: `"data/entities/projectiles/tentacle/tongue_2.png"`
*   **`offset_x`**: Horizontal offset of the sprite from its entity's origin.
    *   Value: `"0"`
*   **`offset_y`**: Vertical offset of the sprite from its entity's origin.
    *   Value: `"4.5"`
*   **`update_transform`**: Determines if the sprite's transform (position, rotation, scale) should be updated automatically.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated automatically.
    *   Value: `"0"` (Disabled)
*   **`z_index`**: Controls the drawing order of the sprite. Higher values are drawn on top.
    *   Value: `"0.82"`