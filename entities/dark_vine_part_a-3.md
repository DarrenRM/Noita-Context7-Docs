---
title: Dark Vine Part A-3
category: entities
---

# Dark Vine Part A-3

This entity defines a single segment of a dark vine, specifically the "A-3" variant. It primarily uses a `SpriteComponent` to render its visual appearance.

## SpriteComponent

This component handles the visual representation of the vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the XML file containing the sprite data for this vine segment. In this case, it points to `data/entities/verlet_chains/vines/vine_parts/vine_dark_a_3.xml`.
*   **`offset_x`**: The horizontal offset of the sprite. Set to `0`.
*   **`offset_y`**: The vertical offset of the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated. Set to `0` (disabled).
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (disabled).