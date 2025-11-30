---
title: Dark Vine Part A - Sprite and Animation
category: entities
---

# Dark Vine Part A - Sprite and Animation

This document describes the sprite and animation data for a specific part of a dark vine entity in Noita.

## Sprite

The sprite defines the visual appearance of the vine part.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts/vine_dark_a.png` - The texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default.

## Animation

This section details the `stand` animation, which is the primary animation for this vine part.

### Key Attributes:

*   **name**: `stand` - The name of this animation.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame in pixels.
*   **frame\_height**: `3` - The height of each individual frame in pixels.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).