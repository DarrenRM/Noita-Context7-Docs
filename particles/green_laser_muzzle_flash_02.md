---
title: Green Laser Muzzle Flash 02
category: particles
---

---

# Green Laser Muzzle Flash 02

This documentation describes the `muzzle_laser_green_02.xml` file, which defines a green laser muzzle flash particle effect for Noita.

## Sprite

The primary visual component of the muzzle flash.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_laser_green_02.png` - The texture file for the particle.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `7` - Vertical offset for the sprite.
*   **default\_animation**: `muzzle` - Specifies the default animation to use.

## RectAnimation

Defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The name of this animation, referenced by the `Sprite` element.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the texture.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).

This animation is a single frame, suggesting a static visual for the muzzle flash.