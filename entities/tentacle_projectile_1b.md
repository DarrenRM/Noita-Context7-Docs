---
title: Tentacle Projectile 1b
category: entities
---

# Tentacle Projectile 1b

This document describes the `tentacle_1b.xml` entity, which defines a specific type of tentacle projectile in Noita.

## Sprite Component

The `SpriteComponent` defines the visual representation of the projectile.

### Key Attributes:

*   **`image_file`**: Specifies the texture file used for the sprite.
    *   Value: `"data/entities/projectiles/tentacle/tentacle_1b.png"`
*   **`offset_x`**: Horizontal offset of the sprite from the entity's origin.
    *   Value: `"0"`
*   **`offset_y`**: Vertical offset of the sprite from the entity's origin.
    *   Value: `"4.5"`
*   **`update_transform`**: Determines if the sprite's transform (position, scale, rotation) should be updated based on the entity's transform.
    *   Value: `"0"` (Sprite transform is static relative to entity)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated based on the entity's rotation.
    *   Value: `"0"` (Sprite rotation is static relative to entity)