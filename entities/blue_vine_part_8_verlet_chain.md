---
title: Blue Vine Part 8 ( Verlet Chain )
category: entities
---

# Blue Vine Part 8 ( Verlet Chain )

This entity defines a single segment of a blue vine, specifically designed for use within Noita'sverlet chain system. It primarily consists of a sprite component to render its visual appearance.

## Sprite Component

The `SpriteComponent` dictates how this vine segment is drawn in the game.

### Key Attributes:

*   **`image_file`**: Specifies the XML file that defines the sprite's appearance. In this case, it points to `data/entities/verlet_chains/vines/vine_parts_blue/vine_b_8.xml`.
*   **`offset_x`**: Horizontal offset for the sprite's position. Set to `0`.
*   **`offset_y`**: Vertical offset for the sprite's position. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, rotation, scale) is updated. Set to `0` (false), meaning it's static relative to its parent entity.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (false), meaning its rotation is static.