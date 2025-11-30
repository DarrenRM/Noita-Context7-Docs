---
title: Eye Particle
category: particles
---

---

# Eye Particle

This document describes the configuration for the "eye" particle effect in Noita, primarily focusing on its visual representation and animation.

## Sprite Configuration

The `Sprite` element defines the visual asset used for the particle.

### Key Attributes:

*   **filename**: `data/particles/eye.png` - Specifies the image file used for the particle's sprite.
*   **offset\_x**: `5.5` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `5.5` - The vertical offset of the sprite's origin.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animation: Explosion

The `RectAnimation` element defines the animation sequence for the particle.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `11` - The width of each individual frame.
*   **frame\_height**: `11` - The height of each individual frame.
*   **frame\_wait**: `0.02` - The time in seconds to wait between frames.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).