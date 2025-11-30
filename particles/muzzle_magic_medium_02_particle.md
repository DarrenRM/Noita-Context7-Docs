---
title: Muzzle Magic Medium 02 Particle
category: particles
---

# Muzzle Magic Medium 02 Particle

This document describes the `muzzle_magic_medium_02.xml` particle effect, commonly used for muzzle flashes in Noita.

## Sprite

The `Sprite` element defines the visual appearance of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_medium_02.png` - The texture file used for the particle.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `7` - Vertical offset for the sprite.
*   **default\_animation**: `muzzle` - Specifies the default animation to play.

## RectAnimation

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The name of this animation, referenced by `default_animation`.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).