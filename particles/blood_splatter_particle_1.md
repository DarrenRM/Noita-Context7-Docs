---
title: Blood Splatter Particle 1
category: particles
---

# Blood Splatter Particle 1

This document describes the configuration for a specific blood splatter particle effect in Noita, designed for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_1.png` - Specifies the texture file used for the sprite.
*   **`offset_x`**: `8` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `8` - Vertical offset for the sprite's origin.

### Animation: `smoke`

The `RectAnimation` element defines the animation sequence for the sprite.

#### Key Attributes:

*   **`name`**: `smoke` - The name of this specific animation.
*   **`frame_count`**: `4` - The total number of frames in the animation.
*   **`frame_width`**: `17` - The width of each individual frame.
*   **`frame_height`**: `17` - The height of each individual frame.
*   **`frame_wait`**: `0.025` - The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: `8` - The number of frames arranged horizontally in the texture file.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays once).
*   **`shrink_by_one_pixel`**: `1` - A flag that likely causes the sprite to shrink by one pixel per frame.
*   **`pos_x`**: `0` - The starting X position of the animation frames within the texture.
*   **`pos_y`**: `1` - The starting Y position of the animation frames within the texture.