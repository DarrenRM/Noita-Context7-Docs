---
title: Pink Shine Particle
category: particles
---

---

# Pink Shine Particle

This document describes the configuration for a pink shine particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The particle uses a sprite with specific visual properties and animation.

### Key Attributes:

*   **filename**: `data/particles/shine_pink.png` - The image file used for the particle.
*   **offset\_x**: `2.5` - Horizontal offset for the sprite.
*   **offset\_y**: `2.5` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The animation to play by default.

## Animation: Explosion

This section details the "explosion" animation used by the particle.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `3` - The total number of frames in the animation.
*   **frame\_width**: `5` - The width of each individual frame.
*   **frame\_height**: `5` - The height of each individual frame.
*   **frame\_wait**: `0.08` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `3` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays once).