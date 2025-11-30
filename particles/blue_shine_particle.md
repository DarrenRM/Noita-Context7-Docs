---
title: Blue Shine Particle
category: particles
---

---

# Blue Shine Particle

This document describes the configuration for a blue shine particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The particle uses a sprite sheet to define its visual appearance and animation.

### Key Attributes:

*   **filename**: `data/particles/shine_blue.png` - Specifies the texture file for the particle.
*   **offset\_x**: `2.5` - Horizontal offset for the sprite.
*   **offset\_y**: `2.5` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animation: Explosion

This section details the "explosion" animation used by the blue shine particle.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `3` - The total number of frames in this animation.
*   **frame\_width**: `5` - The width of each individual animation frame in pixels.
*   **frame\_height**: `5` - The height of each individual animation frame in pixels.
*   **frame\_wait**: `0.04` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `3` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).