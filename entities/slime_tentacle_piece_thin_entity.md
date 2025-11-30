---
title: Slime Tentacle Piece (Thin) Entity
category: entities
---

# Slime Tentacle Piece (Thin) Entity

This document describes the `slime_tentacle_piece_thin.xml` entity, which represents a thin segment of a slime tentacle in Noita.

## Sprite Component

The `SpriteComponent` defines the visual representation of the entity.

### Key Attributes:

*   **`image_file`**: `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin.png`
    *   Specifies the texture file used for this tentacle piece.
*   **`offset_x`**: `0`
    *   Horizontal offset for the sprite.
*   **`offset_y`**: `0.5`
    *   Vertical offset for the sprite.
*   **`update_transform`**: `0`
    *   Indicates whether the sprite's transform (position, scale, rotation) should be updated automatically. `0` means it's not.
*   **`update_transform_rotation`**: `0`
    *   Indicates whether the sprite's rotation should be updated automatically. `0` means it's not.

```xml
<SpriteComponent 
  image_file="data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin.png" 
  offset_x="0"
  offset_y="0.5"
  update_transform="0"
  update_transform_rotation="0" >
</SpriteComponent>
```