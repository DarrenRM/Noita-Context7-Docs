---
title: Large Magic Launcher Muzzle Flash 01
category: particles
---

# Large Magic Launcher Muzzle Flash 01

This documentation describes the particle effect for a large magic launcher's muzzle flash, specifically `muzzle_magic_launcher_large_01.xml`.

## Sprite

This section defines the visual representation of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_launcher_large_01.png` - The image file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset of the sprite.
*   **offset\_y**: `7` - Vertical offset of the sprite.
*   **default\_animation**: `muzzle` - The name of the animation to be used by default.

## RectAnimation

This section defines the animation properties for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position of the animation frame.
*   **pos\_y**: `0` - Starting Y position of the animation frame.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each animation frame.
*   **frame\_height**: `16` - The height of each animation frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).