---
title: Large Blue Magic Launcher Muzzle Flash 02
category: particles
---

# Large Blue Magic Launcher Muzzle Flash 02

This documentation describes the particle effect for a large blue magic launcher's muzzle flash, specifically `muzzle_magic_launcher_large_blue_02.xml`.

## Sprite

The primary visual component of the muzzle flash.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_launcher_large_blue_02.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset for the sprite's position.
*   **offset\_y**: `7` - Vertical offset for the sprite's position.
*   **default\_animation**: `muzzle` - The name of the animation to be played by default.

## RectAnimation

Defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation, linked to `default_animation` in the `Sprite` tag.
*   **pos\_x**: `0` - Starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).