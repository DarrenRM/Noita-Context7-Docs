---
title: Darkball Explosion Particle
category: particles
---

# Darkball Explosion Particle

This document describes the `explosion_064_darkball.xml` particle effect, used for a darkball explosion in Noita.

## Sprite

The `Sprite` element defines the visual appearance of the particle.

### Key Attributes:

*   **filename**: `data/particles/explosion_064_darkball.png` - Specifies the texture file for the particle animation.
*   **offset\_x**: `32` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `32` - The vertical offset of the sprite's origin.
*   **default\_animation**: `explosion` - The name of the default animation to play.

## RectAnimation

The `RectAnimation` element defines a rectangular sprite sheet animation.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - The X position of the animation's starting frame on the sprite sheet.
*   **pos\_y**: `0` - The Y position of the animation's starting frame on the sprite sheet.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `64` - The width of each individual frame.
*   **frame\_height**: `64` - The height of each individual frame.
*   **frame\_wait**: `0.02` - The time in seconds to wait between frames.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no, 1 for yes).