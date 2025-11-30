---
title: Skull Particle
category: particles
---

# Skull Particle

This document describes the configuration for the "skull" particle effect in Noita, primarily focusing on its visual representation and animation.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the animation to be used by default. In this case, it's `"explosion"`.
*   **`filename`**: The path to the sprite sheet containing the particle's graphics. Here, it's `"data/particles/skull.png"`.
*   **`offset_x`**: Horizontal offset for the sprite. Value: `"3.5"`.
*   **`offset_y`**: Vertical offset for the sprite. Value: `"3"`.

## Animation Details

The `RectAnimation` element defines the specific frames and timing for the `"explosion"` animation.

### Key Attributes:

*   **`name`**: The name of this animation, matching the `default_animation` in the `Sprite` element. Value: `"explosion"`.
*   **`frame_count`**: The total number of frames in the animation. Value: `"6"`.
*   **`frame_width`**: The width of each individual frame in pixels. Value: `"8"`.
*   **`frame_height`**: The height of each individual frame in pixels. Value: `"7"`.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet. Value: `"6"`.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next. Value: `"0.09"`.
*   **`loop`**: Determines if the animation should loop. `"0"` indicates no looping (it plays once).
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet. Value: `"0"`.
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet. Value: `"1"`.
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel. Value: `"1"` (true).