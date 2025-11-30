---
title: Muzzle Magic Small 02 Particle
category: particles
---

# Muzzle Magic Small 02 Particle

This document describes the `muzzle_magic_small_02.xml` particle effect, commonly used for small magical muzzle flashes in Noita.

## Sprite

The `Sprite` element defines the visual appearance of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_small_02.png` - Specifies the texture file for the particle.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `7` - Vertical offset for the sprite's origin.
*   **default\_animation**: `muzzle` - The name of the animation to be used by default.

## RectAnimation

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation, referenced by `default_animation`.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no, 1 for yes). In this case, it does not loop.