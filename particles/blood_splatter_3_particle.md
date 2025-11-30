---
title: Blood Splatter 3 Particle
category: particles
---

# Blood Splatter 3 Particle

This document describes the configuration for `bloodsplatter_3.xml`, a particle effect used in Noita.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/bloodsplatters/bloodsplatter_3.png` - Specifies the texture file for the particle.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `8` - Vertical offset for the sprite's origin.
*   **default\_animation**: `smoke` - Sets the default animation to be played.

## Animation Configuration

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `smoke` - The name of this animation, referenced by `default_animation`.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.025` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays once).