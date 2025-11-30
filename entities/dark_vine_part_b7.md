---
title: Dark Vine Part B7
category: entities
---

# Dark Vine Part B7

This entity defines a specific segment of a dark vine, likely used in a "verlet chain" system for dynamic vine growth or movement.

## Sprite Component

This component handles the visual representation of the vine part.

### Key Attributes:

*   **`image_file`**: Specifies the sprite to be used. In this case, it points to `data/entities/verlet_chains/vines/vine_parts/vine_dark_b_7.xml`. This suggests a separate XML file defines the actual sprite properties.
*   **`offset_x`**: Horizontal offset of the sprite. Set to `0`.
*   **`offset_y`**: Vertical offset of the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated. Set to `0` (disabled).
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (disabled).

## Entity

The root element for this entity. It contains the `SpriteComponent`.