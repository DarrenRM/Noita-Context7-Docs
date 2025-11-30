---
title: Small Magic Muzzle Flash 01
category: particles
---

# Small Magic Muzzle Flash 01

This particle effect defines a small, magical muzzle flash for weapons or spells in Noita. It's a simple, single-frame animation.

## Sprite

The primary visual component of the muzzle flash.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_small_01.png` - The texture file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `7` - Vertical offset of the sprite's origin.
*   **default\_animation**: `"muzzle"` - Specifies the default animation to play.

## RectAnimation

Defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `"muzzle"` - The name of this animation, referenced by the `Sprite` element.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).