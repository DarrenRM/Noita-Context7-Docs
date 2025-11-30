---
title: Large Blue Magic Launcher Muzzle Flash 04
category: particles
---

# Large Blue Magic Launcher Muzzle Flash 04

This documentation describes a muzzle flash particle effect for the game Noita, specifically designed for a large blue magic launcher.

## Sprite

The primary visual component of the muzzle flash.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_launcher_large_blue_04.png` - The image file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `7` - Vertical offset of the sprite's origin.
*   **default\_animation**: `muzzle` - Specifies the default animation to play.

## RectAnimation

Defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The name of this animation, referenced by the `Sprite` element.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no, 1 for yes). In this case, it plays once.