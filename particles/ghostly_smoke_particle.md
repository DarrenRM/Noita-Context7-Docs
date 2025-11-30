---
title: Ghostly Smoke Particle
category: particles
---

---

# Ghostly Smoke Particle

This document describes the configuration for the "Ghostly Smoke" particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/smoke_ghostly.png` - Specifies the texture file used for the particle.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `8` - Vertical offset for the sprite's origin.
*   **default\_animation**: `smoke` - The name of the animation to play by default.

### Animation: `smoke`

The `RectAnimation` element defines the sprite sheet animation.

#### Key Attributes:

*   **name**: `smoke` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position on the sprite sheet.
*   **pos\_y**: `0` - Starting Y position on the sprite sheet.
*   **frame\_count**: `8` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.03` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `8` - The number of frames in a single row of the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no, 1 for yes). In this case, it does not loop.