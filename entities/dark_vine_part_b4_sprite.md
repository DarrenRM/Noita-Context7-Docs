---
title: Dark Vine Part B4 Sprite
category: entities
---

# Dark Vine Part B4 Sprite

This documentation describes the sprite data for a specific part of a dark vine entity in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual representation of the entity part.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts/vine_dark_b.png` - The path to the sprite image file.
*   **offset\_x**: `0` - Horizontal offset for the sprite.
*   **offset\_y**: `0` - Vertical offset for the sprite.
*   **default\_animation**: `stand` - The animation to play by default.

## Animation: `stand`

The `<RectAnimation>` tag defines the animation frames for the sprite.

### Key Attributes:

*   **name**: `stand` - The name of this animation.
*   **pos\_x**: `12` - The X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each animation frame.
*   **frame\_height**: `3` - The height of each animation frame.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).