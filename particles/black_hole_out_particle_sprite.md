---
title: Black Hole Out Particle Sprite
category: particles
---

# Black Hole Out Particle Sprite

This document describes the sprite configuration for the "black_hole_out" particle effect in Noita.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`default_animation`**: Specifies the default animation to use, which is "explosion" in this case.
*   **`filename`**: The path to the sprite sheet image file.
    *   `data/particles/black_hole_out.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `12`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `12`

## Animation: "explosion"

The "explosion" animation is defined within a `<RectAnimation>` tag.

### Key Attributes:

*   **`name`**: The name of the animation.
    *   `explosion`
*   **`frame_count`**: The total number of frames in the animation.
    *   `7`
*   **`frame_width`**: The width of each individual frame.
    *   `25`
*   **`frame_height`**: The height of each individual frame.
    *   `25`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `7`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.02`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel.
    *   `1`
*   **`pos_x`**: Starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position of the animation frames within the sprite sheet.
    *   `1`