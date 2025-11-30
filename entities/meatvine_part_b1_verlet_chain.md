---
title: Meatvine Part B1 Verlet Chain
category: entities
---

# Meatvine Part B1 Verlet Chain

This entity defines a single segment of the "meatvine" verlet chain, specifically the "B1" variant. It primarily consists of a sprite component to render its visual appearance.

## Sprite Component

The `SpriteComponent` dictates how this entity is visually represented in the game.

### Key Attributes:

*   **`image_file`**: Specifies the image file used for the sprite. In this case, it points to `data/entities/verlet_chains/meatvine/vine_parts/vine_b_1.xml`, which likely contains the actual sprite data for this vine segment.
*   **`offset_x`**: Horizontal offset for the sprite. Set to `0`.
*   **`offset_y`**: Vertical offset for the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, rotation, scale) is updated. Set to `0`, meaning it's static in this regard.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0`, meaning it's static in rotation.