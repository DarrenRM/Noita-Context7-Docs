---
title: Frozen Blast Particle
category: particles
---

---

# Frozen Blast Particle

This document describes the configuration for a particle effect in Noita, specifically a "frozen blast" visual.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/blast_out.png` - Specifies the image file used for the particle's sprite.
*   **offset\_x**: `32` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `32` - The vertical offset of the sprite's origin.
*   **default\_animation**: `explosion` - The name of the animation to play by default.
*   **color\_r**: `0.8` - Red component of the particle's color (0.0 to 1.0).
*   **color\_g**: `0.96` - Green component of the particle's color (0.0 to 1.0).
*   **color\_b**: `1` - Blue component of the particle's color (0.0 to 1.0).

## Animation Definition

The `<RectAnimation>` element defines how the sprite is animated.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation, referenced by `default_animation`.
*   **pos\_x**: `0` - The starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - The starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `64` - The width of each individual animation frame.
*   **frame\_height**: `64` - The height of each individual animation frame.
*   **frame\_wait**: `0.02` - The time in seconds to wait between displaying each frame.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).