---
title: Large Muzzle Flash 05 Particle
category: particles
---

# Large Muzzle Flash 05 Particle

This document describes the configuration for a specific muzzle flash particle effect in Noita, designed for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_large_05.png` - Specifies the texture file used for the particle.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `7` - Vertical offset for the sprite's origin.
*   **default\_animation**: `muzzle` - The name of the animation to be played by default.

## Animation Configuration

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation, referenced by `default_animation`.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).

This particle is a simple, single-frame muzzle flash with a short duration.