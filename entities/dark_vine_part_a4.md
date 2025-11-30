---
title: Dark Vine Part A4
category: entities
---

# Dark Vine Part A4

This entity defines a single segment of a dark blue vine, specifically the 'A4' variant. It's a visual component designed to be part of a largerverlet chain.

## SpriteComponent

This is the primary component responsible for rendering the visual appearance of the vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the XML file that defines the sprite's visual properties. In this case, it points to `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_a_4.xml`.
*   **`offset_x`**: The horizontal offset of the sprite from the entity's origin. Set to `0`.
*   **`offset_y`**: The vertical offset of the sprite from the entity's origin. Set to `1.5`.
*   **`update_transform`**: A flag indicating whether the sprite's transform (position, scale, rotation) should be updated. Set to `0` (false), meaning it's static relative to its parent.
*   **`update_transform_rotation`**: A flag indicating whether the sprite's rotation should be updated. Set to `0` (false), meaning it's static in rotation.