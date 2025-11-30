---
title: Tiny Pink Smoke Cloud Particle
category: particles
---

# Tiny Pink Smoke Cloud Particle

This document describes the configuration for a small, pink smoke cloud particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The particle uses a sprite sheet to define its visual appearance and animation.

### Key Attributes:

*   **filename**: `data/particles/smoke_cloud_pink_3.png` - Specifies the texture file for the particle.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `10` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animation: `explosion`

This section details the animation sequence for the smoke cloud.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `8` - The total number of frames in the animation.
*   **frame\_width**: `20` - The width of each individual frame in pixels.
*   **frame\_height**: `20` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.09` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).