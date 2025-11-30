---
title: Green Smoke Cloud Particle
category: particles
---

# Green Smoke Cloud Particle

This document describes the configuration for a green smoke cloud particle effect in Noita, suitable for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: Specifies the texture file for the particle.
    *   `data/particles/smoke_cloud_green_3.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `10`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `10`
*   **`default_animation`**: The name of the animation to play by default.
    *   `explosion`

## Animation: `explosion`

The `RectAnimation` element defines the frames and timing for the "explosion" animation.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `explosion`
*   **`pos_x`**: Starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position of the animation frames within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `8`
*   **`frame_width`**: The width of each individual frame.
    *   `20`
*   **`frame_height`**: The height of each individual frame.
    *   `20`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.09`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `8`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`