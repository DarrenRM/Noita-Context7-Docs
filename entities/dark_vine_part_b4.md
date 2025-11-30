---
title: Dark Vine Part B4
category: entities
---

# Dark Vine Part B4

This entity defines a segment of a dark vine, specifically the 'B4' variant. It primarily uses a sprite to visually represent this vine segment.

## Sprite Component

The `SpriteComponent` is the core visual element for this entity.

### Key Attributes:

*   **`image_file`**: Specifies the sprite's image. In this case, it points to `data/entities/verlet_chains/vines/vine_parts/vine_dark_b_4.xml`. This indicates the visual asset used for this vine segment.
*   **`offset_x`**: Horizontal offset for the sprite. Set to `0`.
*   **`offset_y`**: Vertical offset for the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated. Set to `0` (false), meaning it's static in its transform.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (false), meaning its rotation is static.