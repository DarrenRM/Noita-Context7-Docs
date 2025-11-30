---
title: Small Tentacle Projectile 3 Sprite
category: entities
---

# Small Tentacle Projectile 3 Sprite

This document describes the sprite component for the "smalltentacle_3" projectile entity in Noita.

## SpriteComponent

This component defines the visual representation of the projectile.

### Key Attributes:

*   **`image_file`**: `data/entities/projectiles/tentacle/smalltentacle_3.png`
    *   Specifies the texture file used for the sprite.
*   **`offset_x`**: `0`
    *   The horizontal offset of the sprite from the entity's origin.
*   **`offset_y`**: `4.5`
    *   The vertical offset of the sprite from the entity's origin.
*   **`update_transform`**: `0`
    *   Indicates whether the sprite's transform (position, scale) should be updated automatically. `0` means it's static relative to the entity's base transform.
*   **`update_transform_rotation`**: `0`
    *   Indicates whether the sprite's rotation should be updated automatically. `0` means it's static relative to the entity's base rotation.

```xml
<Entity >
  <SpriteComponent 
    image_file="data/entities/projectiles/tentacle/smalltentacle_3.png" 
    offset_x="0"
    offset_y="4.5"
    update_transform="0"
    update_transform_rotation="0" >
  </SpriteComponent>
</Entity>
```