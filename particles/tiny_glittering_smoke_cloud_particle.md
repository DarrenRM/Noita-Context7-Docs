---
title: Tiny Glittering Smoke Cloud Particle
category: particles
---

# Tiny Glittering Smoke Cloud Particle

This document describes the configuration for a small, glittering smoke cloud particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The particle uses a sprite sheet to define its visual appearance and animation.

### Key Attributes:

*   **filename**: `data/particles/smoke_cloud_tiny_glitter_1.png` - Specifies the texture file for the particle.
*   **offset\_x**: `10` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `10` - Vertical offset for the sprite's origin.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animation: Explosion

This section details the "explosion" animation used by the particle.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `10` - The total number of frames in the animation.
*   **frame\_width**: `20` - The width of each individual animation frame in pixels.
*   **frame\_height**: `20` - The height of each individual animation frame in pixels.
*   **frame\_wait**: `0.10` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).