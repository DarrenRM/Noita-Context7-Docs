---
title: Pink Muzzle Flash 05 Particle
category: particles
---

# Pink Muzzle Flash 05 Particle

This document describes the configuration for a specific muzzle flash particle effect in Noita, designed to produce a pink visual burst.

## Sprite Configuration

The primary visual component of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_pink_05.png` - Specifies the image file used for the particle's texture.
*   **offset\_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `7` - The vertical offset of the sprite's origin.
*   **default\_animation**: `muzzle` - The name of the animation to be used by default for this sprite.

## Animation Details

The `<RectAnimation>` element defines how the sprite is animated.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation, referenced by the sprite.
*   **pos\_x**: `0` - The starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - The starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `16` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no, 1 for yes). In this case, it does not loop.