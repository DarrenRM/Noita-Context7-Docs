---
title: Vine Part A2 Sprite
category: entities
---

# Vine Part A2 Sprite

This document describes the sprite and animation data for `vine_a_2.xml`, a component of the vine entity in Noita.

## Sprite

The sprite defines the visual appearance of the vine part.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts/vine_a.png` - The texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation: `stand`

This section details the `stand` animation for the vine part.

### Key Attributes:

*   **name**: `"stand"` - The name of the animation.
*   **pos\_x**: `4` - X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `4` - The width of each animation frame.
*   **frame\_height**: `3` - The height of each animation frame.
*   **frame\_wait**: `1` - The duration (in game frames) each frame is displayed.
*   **frames\_per\_row**: `8` - The number of frames that fit horizontally in a single row of the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).