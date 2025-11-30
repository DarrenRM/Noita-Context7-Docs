---
title: Dark Vine Part A5
category: entities
---

# Dark Vine Part A5

This entity defines a single segment of a dark vine, specifically the 'A5' variant. It primarily utilizes a `SpriteComponent` to render its visual appearance.

## Sprite Component

The `SpriteComponent` dictates how this vine segment is drawn.

### Key Attributes:

*   **`image_file`**: Specifies the graphical asset used for this vine segment.
    *   Value: `"data/entities/verlet_chains/vines/vine_parts/vine_dark_a_5.xml"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"0"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"1.5"`
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated.
    *   Value: `"0"` (Disabled)