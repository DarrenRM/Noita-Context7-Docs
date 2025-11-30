---
title: Green Blood Splatter Particle
category: particles
---

# Green Blood Splatter Particle

This document describes the configuration for a green blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to use. Here, it's set to "smoke".
*   **`filename`**: The path to the sprite sheet containing the animation frames.
    *   `data/particles/bloodsplatters/bloodsplatter_green_2.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `8`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `8`

## Animation Details

The `RectAnimation` element defines the specific frames and timing for the "smoke" animation.

### Key Attributes:

*   **`name`**: The name of this animation, matching `default_animation`.
    *   `smoke`
*   **`frame_count`**: The total number of frames in the animation.
    *   `4`
*   **`frame_width`**: The width of each individual frame.
    *   `17`
*   **`frame_height`**: The height of each individual frame.
    *   `17`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `8`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.025`
*   **`loop`**: Whether the animation should loop. `0` indicates no looping.
    *   `0`
*   **`pos_x`**: Starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position of the animation frames within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel.
    *   `1`