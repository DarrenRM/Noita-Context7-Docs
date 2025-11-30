---
title: Large Launcher Muzzle Flash 04
category: particles
---

# Large Launcher Muzzle Flash 04

This documentation describes the particle effect for a large launcher's muzzle flash, specifically `muzzle_launcher_large_04.xml`.

## Sprite

The primary visual component of the muzzle flash.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_launcher_large_04.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `7` - Vertical offset of the sprite's origin.
*   **default\_animation**: `muzzle` - The name of the animation to be played by default.

## RectAnimation

Defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation, referenced by the `Sprite` element.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame in pixels.
*   **frame\_height**: `16` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no, 1 for yes). In this case, it does not loop.