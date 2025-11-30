---
title: Green Shine Particle
category: particles
---

# Green Shine Particle

This document describes the configuration for a green shine particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The particle uses a sprite with specific positioning and animation settings.

### Key Attributes:

*   **filename**: `data/particles/shine_green.png` - The image file used for the particle.
*   **offset\_x**: `2.5` - Horizontal offset for the sprite.
*   **offset\_y**: `2.5` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animation: "explosion"

This section details the "explosion" animation for the green shine particle.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `3` - The total number of frames in the animation.
*   **frame\_width**: `5` - The width of each individual frame.
*   **frame\_height**: `5` - The height of each individual frame.
*   **frame\_wait**: `0.08` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `3` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).