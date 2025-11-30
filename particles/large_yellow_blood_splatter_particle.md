---
title: Large Yellow Blood Splatter Particle
category: particles
---

# Large Yellow Blood Splatter Particle

This document describes the configuration for a large yellow blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the sprite.
    *   `data/particles/bloodsplatters/bloodsplatter_large_yellow_2.png`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   `16`
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   `16`
*   **`default_animation`**: The name of the animation to play by default.
    *   `smoke`

## Animation Details

The `<RectAnimation>` element defines how the sprite frames are arranged and animated.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `smoke`
*   **`frame_count`**: The total number of frames in the animation.
    *   `6`
*   **`frame_width`**: The width of each individual frame.
    *   `33`
*   **`frame_height`**: The height of each individual frame.
    *   `33`
*   **`frames_per_row`**: The number of frames arranged horizontally in the texture.
    *   `8`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.03`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`
*   **`pos_x`**: The starting X-coordinate of the animation frames within the texture.
    *   `0`
*   **`pos_y`**: The starting Y-coordinate of the animation frames within the texture.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel. `1` means true.
    *   `1`