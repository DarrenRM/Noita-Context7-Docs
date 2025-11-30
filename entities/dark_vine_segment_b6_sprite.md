---
title: Dark Vine Segment B6 Sprite
category: entities
---

# Dark Vine Segment B6 Sprite

This document describes the sprite data for a segment of a dark vine, specifically `vine_dark_b_6`.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts/vine_dark_b.png` - The image file containing the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation

The sprite uses a single animation named `"stand"`.

### Key Attributes:

*   **name**: `"stand"`
*   **pos\_x**: `20` - X-coordinate of the top-left corner of the sprite frame within the texture.
*   **pos\_y**: `0` - Y-coordinate of the top-left corner of the sprite frame within the texture.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `4` - The width of each individual frame.
*   **frame\_height**: `3` - The height of each individual frame.
*   **frame\_wait**: `1` - The duration each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).