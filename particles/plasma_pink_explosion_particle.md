---
title: Plasma Pink Explosion Particle
category: particles
---

# Plasma Pink Explosion Particle

This document describes the configuration for a plasma pink explosion particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play, which is "explosion" in this case.
*   **`filename`**: The path to the sprite sheet containing the animation frames.
    *   `data/particles/explosion_016_plasma_pink.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `8`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `8`

### Animation: `explosion`

The `RectAnimation` element defines the parameters for the "explosion" animation.

#### Key Attributes:

*   **`frame_count`**: The total number of frames in the animation.
    *   `9`
*   **`frame_height`**: The height of each individual frame.
    *   `17`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.021`
*   **`frame_width`**: The width of each individual frame.
    *   `17`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `8`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping (plays once).
    *   `0`
*   **`name`**: The name of this animation, referenced by `default_animation`.
    *   `explosion`
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel. `1` means true.
    *   `1`