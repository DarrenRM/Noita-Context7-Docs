---
title: Smoke Particle 03
category: particles
---

# Smoke Particle 03

This document describes the configuration for a specific smoke particle effect in Noita, identified as `smoke_03`. It details the visual representation and animation properties of this particle.

## Sprite Configuration

The `Sprite` element defines the visual asset used for the particle.

### Key Attributes:

*   **filename**: `data/particles/smoke_03.png` - Specifies the image file containing the particle's texture.
*   **offset\_x**: `4` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `4` - The vertical offset of the sprite's origin.
*   **default\_animation**: `smoke` - The name of the animation to be used by default for this sprite.

## Animation Configuration

The `RectAnimation` element defines how the sprite is animated.

### Key Attributes:

*   **name**: `smoke` - The identifier for this animation, referenced by the `Sprite` element.
*   **pos\_x**: `0` - The starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - The starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `8` - The width of each individual animation frame.
*   **frame\_height**: `8` - The height of each individual animation frame.
*   **frame\_wait**: `0.06` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop. `0` means it will not loop (play once).