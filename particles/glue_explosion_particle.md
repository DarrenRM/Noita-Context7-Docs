---
title: Glue Explosion Particle
category: particles
---

# Glue Explosion Particle

This document describes the configuration for a specific particle effect in Noita, designed to represent a "glue explosion."

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play, which is "explosion" in this case.
*   **`filename`**: The path to the sprite sheet containing the animation frames.
    *   `data/particles/explosion_032_glue.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `16`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `16`

### RectAnimation: `explosion`

This nested element defines the parameters for the "explosion" animation.

#### Key Attributes:

*   **`name`**: The name of this specific animation.
    *   `explosion`
*   **`frame_count`**: The total number of frames in the animation.
    *   `7`
*   **`frame_width`**: The width of each individual frame.
    *   `33`
*   **`frame_height`**: The height of each individual frame.
    *   `33`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `7`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.04`
*   **`loop`**: Whether the animation should loop. `0` indicates no looping (plays once).
    *   `0`
*   **`pos_x`**: X-coordinate of the top-left corner of the animation within the sprite sheet.
    *   `0`
*   **`pos_y`**: Y-coordinate of the top-left corner of the animation within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel.
    *   `1`