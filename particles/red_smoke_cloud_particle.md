---
title: Red Smoke Cloud Particle
category: particles
---

---

# Red Smoke Cloud Particle

This document describes the configuration for a red smoke cloud particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: Specifies the texture file for the particle sprite.
    *   `data/particles/smoke_cloud_red_1.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `10`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `10`
*   **`default_animation`**: The name of the default animation to play.
    *   `explosion`

## Animation Details

The particle utilizes a rectangular animation for its visual sequence.

### `explosion` Animation:

*   **`name`**: `explosion`
*   **`pos_x`**: Starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position of the animation frames within the sprite sheet.
    *   `0`
*   **`frame_count`**: Total number of frames in the animation.
    *   `16`
*   **`frame_width`**: Width of each individual frame.
    *   `20`
*   **`frame_height`**: Height of each individual frame.
    *   `20`
*   **`frame_wait`**: Time in seconds each frame is displayed before transitioning to the next.
    *   `0.05`
*   **`frames_per_row`**: Number of frames arranged horizontally in the sprite sheet.
    *   `16`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`