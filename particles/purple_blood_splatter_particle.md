---
title: Purple Blood Splatter Particle
category: particles
---

# Purple Blood Splatter Particle

This document describes the configuration for a purple blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`default_animation`**: Specifies the default animation to play. Here, it's set to `"smoke"`.
*   **`filename`**: The path to the sprite sheet used for the particle.
    *   `data/particles/bloodsplatters/bloodsplatter_purple_2.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `8`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `8`

## Animation Details

The `<RectAnimation>` element defines how the sprite sheet is used to create animation frames.

### Key Attributes:

*   **`name`**: The name of this specific animation.
    *   `"smoke"`
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
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`
*   **`pos_x`**: Starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position of the animation frames within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag to indicate if frames should shrink by one pixel.
    *   `1`