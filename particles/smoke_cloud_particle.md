---
title: Smoke Cloud Particle
category: particles
---

---

# Smoke Cloud Particle

This document describes the configuration for a smoke cloud particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/smoke_cloud_2.png` - Specifies the texture file used for the particle.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `10` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animation: Explosion

The `RectAnimation` element defines a specific animation sequence.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `16` - The total number of frames in this animation.
*   **frame\_width**: `20` - The width of each individual frame.
*   **frame\_height**: `20` - The height of each individual frame.
*   **frame\_wait**: `0.05` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `16` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).