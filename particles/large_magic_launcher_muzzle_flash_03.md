---
title: Large Magic Launcher Muzzle Flash 03
category: particles
---

---

# Large Magic Launcher Muzzle Flash 03

This documentation describes the particle effect for a large magic launcher's muzzle flash, specifically `muzzle_magic_launcher_large_03.xml`.

## Sprite

The `Sprite` element defines the visual appearance of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_launcher_large_03.png` - The texture file used for the muzzle flash.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `7` - Vertical offset for the sprite's origin.
*   **default\_animation**: `muzzle` - The name of the animation to play by default.

## RectAnimation

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame in pixels.
*   **frame\_height**: `16` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the texture.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).

This animation is a single frame, meaning it's a static image displayed for a short duration.