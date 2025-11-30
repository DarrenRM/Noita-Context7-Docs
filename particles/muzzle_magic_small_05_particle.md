---
title: Muzzle Magic Small 05 Particle
category: particles
---

# Muzzle Magic Small 05 Particle

This documentation describes the `muzzle_magic_small_05.xml` particle file, which defines a small, magical muzzle flash effect for Noita.

## Sprite

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_small_05.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `7` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"muzzle"` - The name of the default animation to play.

## RectAnimation

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `"muzzle"` - The name of this animation, referenced by the `Sprite` element.
*   **pos\_x**: `0` - The starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each animation frame.
*   **frame\_height**: `16` - The height of each animation frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).