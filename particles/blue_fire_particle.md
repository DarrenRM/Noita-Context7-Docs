---
title: Blue Fire Particle
category: particles
---

---

# Blue Fire Particle

This document describes the configuration for the blue fire particle effect in Noita, primarily focusing on its visual representation and animation.

## Sprite Configuration

The `Sprite` element defines the visual asset used for the particle.

### Key Attributes:

*   **filename**: `data/particles/fire_blue.png` - Specifies the image file containing the particle's sprite sheet.
*   **offset\_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `8` - The vertical offset of the sprite's origin.
*   **default\_animation**: `explosion` - The name of the animation to be played by default.

## Animation: Explosion

The `RectAnimation` element defines the animation sequence for the particle.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `7` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame in pixels.
*   **frame\_height**: `16` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.03` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop. `0` means it will not loop (play once).