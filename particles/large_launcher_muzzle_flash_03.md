---
title: Large Launcher Muzzle Flash 03
category: particles
---

# Large Launcher Muzzle Flash 03

This documentation describes the particle effect for a large launcher muzzle flash, specifically `muzzle_launcher_large_03.xml`.

## Sprite

The primary visual component of the muzzle flash.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_launcher_large_03.png` - The image file used for the particle.
*   **offset\_x**: `8` - Horizontal offset of the sprite.
*   **offset\_y**: `7` - Vertical offset of the sprite.
*   **default\_animation**: `muzzle` - The name of the animation to play by default.

## RectAnimation

Defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation.
*   **pos\_x**: `0` - X position within the sprite sheet.
*   **pos\_y**: `0` - Y position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).