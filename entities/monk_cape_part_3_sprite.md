---
title: Monk Cape Part 3 Sprite
category: entities
---

# Monk Cape Part 3 Sprite

This document describes the sprite data for a part of the Monk's cape in Noita.

## Sprite

The primary sprite for this cape part is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/monk_cape/parts/cape_3.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - The horizontal offset of the sprite.
*   **offset\_y**: `0` - The vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animation

The sprite utilizes a single animation named "stand".

### Key Attributes:

*   **name**: `"stand"` - The name of the animation.
*   **pos\_x**: `0` - The X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `8` - The width of each individual animation frame.
*   **frame\_height**: `24` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).