---
title: Muzzle Magic Large 02 Particle
category: particles
---

# Muzzle Magic Large 02 Particle

This document describes the `muzzle_magic_large_02.xml` particle definition, used for a large, magical muzzle flash effect in Noita.

## Sprite Definition

The primary visual component of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_large_02.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `7` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"muzzle"` - The name of the default animation to play for this sprite.

## Animation Definition

The particle utilizes a single animation named "muzzle" to control its visual playback.

### Key Attributes:

*   **name**: `"muzzle"` - The identifier for this animation.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame in pixels.
*   **frame\_height**: `16` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation should not loop (play only once).