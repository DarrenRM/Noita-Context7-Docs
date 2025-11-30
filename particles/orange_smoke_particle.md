---
title: Orange Smoke Particle
category: particles
---

---

# Orange Smoke Particle

This document describes the configuration for the orange smoke particle effect in Noita, primarily focusing on its visual representation and animation.

## Sprite Configuration

The `Sprite` element defines the visual asset used for the particle.

### Key Attributes:

*   **filename**: `data/particles/smoke_orange.png` - Specifies the image file containing the particle's sprite sheet.
*   **offset\_x**: `8.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `8` - Vertical offset for the sprite's origin.
*   **default\_animation**: `smoke` - The name of the animation to be used by default for this sprite.

## Animation Configuration

The `RectAnimation` element defines how the sprite sheet is used to create an animation.

### Key Attributes:

*   **name**: `smoke` - The identifier for this animation, referenced by the `Sprite` element.
*   **pos\_x**: `0` - Starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `8` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame in pixels.
*   **frame\_height**: `16` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.03` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop. `0` means it will not loop (play once).

This configuration creates a simple, non-looping animation of orange smoke using a 16x16 pixel sprite sheet with 8 frames.