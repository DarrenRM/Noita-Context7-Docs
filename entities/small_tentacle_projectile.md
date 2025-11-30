---
title: Small Tentacle Projectile
category: entities
---

---

# Small Tentacle Projectile

This document describes the `smalltentacle_0.xml` entity, which defines a small tentacle projectile in Noita.

## Entity Definition

The core of this entity is its `SpriteComponent`, which dictates its visual representation.

### SpriteComponent

This component handles the visual aspects of the projectile.

*   **`image_file`**: `data/entities/projectiles/tentacle/smalltentacle_0.png`
    *   Specifies the texture file used for the tentacle sprite.
*   **`offset_x`**: `0`
    *   The horizontal offset of the sprite from the entity's origin.
*   **`offset_y`**: `4.5`
    *   The vertical offset of the sprite from the entity's origin.
*   **`update_transform`**: `0`
    *   Indicates whether the sprite's transform (position, scale) should be updated based on the entity's transform. `0` means it's static relative to the entity.
*   **`update_transform_rotation`**: `0`
    *   Indicates whether the sprite's rotation should be updated based on the entity's rotation. `0` means it's static relative to the entity.