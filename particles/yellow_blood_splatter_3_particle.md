---
title: Yellow Blood Splatter 3 Particle
category: particles
---

# Yellow Blood Splatter 3 Particle

This document describes the `bloodsplatter_yellow_3.xml` particle definition, used for visual effects in Noita.

## Sprite Definition

The primary visual component is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/bloodsplatters/bloodsplatter_yellow_3.png` - Specifies the image file for the particle's texture.
*   **offset\_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `8` - The vertical offset of the sprite's origin.
*   **default\_animation**: `smoke` - The name of the default animation to play when the particle is spawned.

## Animation Definition

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **name**: `smoke` - The identifier for this animation, referenced by `default_animation`.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `4` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.025` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).