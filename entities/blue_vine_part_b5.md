---
title: Blue Vine Part B5
category: entities
---

# Blue Vine Part B5

This entity defines a single segment of a blue vine, specifically the "B5" variant. It primarily uses a sprite to visually represent the vine segment.

## Sprite Component

The `SpriteComponent` is responsible for rendering the visual appearance of the vine part.

### Key Attributes:

*   **`image_file`**: Specifies the XML file containing the sprite's definition. In this case, it points to `data/entities/verlet_chains/vines/vine_parts_blue/vine_b_5.xml`.
*   **`offset_x`**: The horizontal offset of the sprite from the entity's origin. Set to `0`.
*   **`offset_y`**: The vertical offset of the sprite from the entity's origin. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated. Set to `0` (disabled).
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (disabled).