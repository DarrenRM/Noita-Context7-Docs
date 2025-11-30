---
title: Vine A Part 1 Sprite
category: entities
---

# Vine A Part 1 Sprite

This document describes the sprite data for a segment of vine, specifically `vine_a_1.xml`.

## Sprite

The primary sprite for this vine segment is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts/vine_a.png` - The image file containing the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation to play by default.

## Animation

The sprite uses a single animation named "stand".

### Key Attributes:

*   **name**: `stand` - The name of the animation.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame.
*   **frame\_height**: `3` - The height of each individual frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).