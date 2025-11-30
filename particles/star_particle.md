---
title: Star Particle
category: particles
---

# Star Particle

This document describes the configuration for the "star" particle effect in Noita, focusing on its visual representation and animation.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the sprite.
    *   `data/particles/star.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `5.5`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `5.5`
*   **`default_animation`**: The name of the animation to play by default.
    *   `default`

## Animation Details

The `RectAnimation` element defines the specific animation frames and timing.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `default`
*   **`pos_x`**: X-coordinate of the top-left corner of the animation frame within the sprite sheet.
    *   `0`
*   **`pos_y`**: Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `3`
*   **`frame_width`**: The width of each individual animation frame.
    *   `11`
*   **`frame_height`**: The height of each individual animation frame.
    *   `11`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.03`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `3`
*   **`loop`**: Determines if the animation should loop.
    *   `1` (meaning true, the animation will loop)