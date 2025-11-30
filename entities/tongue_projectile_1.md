---
title: Tongue Projectile 1
category: entities
---

---

# Tongue Projectile 1

This document describes the `tongue_1.xml` entity, which defines a basic tongue projectile in Noita.

## Sprite Component

The `SpriteComponent` handles the visual representation of the projectile.

### Key Attributes:

*   **`image_file`**: Specifies the texture used for the sprite.
    *   Value: `data/entities/projectiles/tentacle/tongue_1.png`
*   **`offset_x`**: Horizontal offset of the sprite from the entity's origin.
    *   Value: `0`
*   **`offset_y`**: Vertical offset of the sprite from the entity's origin.
    *   Value: `4.5`
*   **`z_index`**: Determines the rendering order of the sprite. Higher values are rendered on top.
    *   Value: `0.81`
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) updates automatically.
    *   Value: `0` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation updates automatically.
    *   Value: `0` (Disabled)