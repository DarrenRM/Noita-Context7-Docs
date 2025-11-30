---
title: Large Pink Muzzle Flash 04
category: particles
---

# Large Pink Muzzle Flash 04

This particle effect simulates a large, pink muzzle flash.

## Sprite

The visual representation of the muzzle flash.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_large_pink_04.png` - The texture file for the sprite.
*   **offset\_x**: `8` - Horizontal offset of the sprite.
*   **offset\_y**: `7` - Vertical offset of the sprite.
*   **default\_animation**: `muzzle` - The name of the default animation to play.

## RectAnimation

Defines the animation for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each animation frame.
*   **frame\_height**: `16` - The height of each animation frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames in a single row of the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no, 1 for yes).