---
title: Dark Vine Part B (8)
category: entities
---

# Dark Vine Part B (8)

This entity defines a segment of a dark vine, specifically the eighth variant in the `vine_dark_verlet_b` chain. It primarily utilizes a sprite to visually represent this vine segment.

## Sprite Component

The `SpriteComponent` is the core element for visual representation.

### Key Attributes:

*   **`image_file`**: Specifies the sprite image to be used. In this case, it points to `data/entities/verlet_chains/vines/vine_parts/vine_dark_b_8.xml`. This likely contains the actual sprite data or references to it.
*   **`offset_x`**: Horizontal offset for the sprite. Set to `0`.
*   **`offset_y`**: Vertical offset for the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated. Set to `0` (disabled).
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (disabled).

This configuration suggests that the sprite for this vine segment is static and its position is determined by its parent entity or theverlet chain system.