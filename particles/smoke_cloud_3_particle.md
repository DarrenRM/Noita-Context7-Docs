---
title: Smoke Cloud 3 Particle
category: particles
---

---

# Smoke Cloud 3 Particle

This document describes the configuration for the "Smoke Cloud 3" particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/smoke_cloud_3.png` - Specifies the texture file used for the particle.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `10` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The name of the default animation to play.

## Animation: Explosion

The particle utilizes a rectangular animation named "explosion".

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `6` - The total number of frames in the animation.
*   **frame\_width**: `20` - The width of each individual frame.
*   **frame\_height**: `20` - The height of each individual frame.
*   **frame\_wait**: `0.06` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).