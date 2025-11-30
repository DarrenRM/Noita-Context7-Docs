---
title: Tiny Smoke Cloud Particle
category: particles
---

---

# Tiny Smoke Cloud Particle

This document describes the configuration for a small, ephemeral smoke cloud particle effect in Noita, suitable for AI-assisted modding.

## Sprite Configuration

The particle uses a sprite sheet to define its visual appearance and animation.

### Key Attributes:

*   **filename**: `data/particles/smoke_cloud_tiny_2.png` - The path to the sprite sheet image.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `10` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animation: `explosion`

This animation defines the sequence of frames that make up the smoke cloud's visual progression.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `6` - The total number of frames in the animation.
*   **frame\_width**: `20` - The width of each individual frame in pixels.
*   **frame\_height**: `20` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.06` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).

This particle is designed to be a quick, dissipating puff of smoke, likely used for minor impacts or environmental effects.