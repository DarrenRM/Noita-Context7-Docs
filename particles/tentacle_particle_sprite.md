---
title: Tentacle Particle Sprite
category: particles
---

---

# Tentacle Particle Sprite

This document describes the sprite configuration for the "tentacle" particle effect in Noita.

## Sprite Configuration

The primary sprite configuration defines the visual appearance and animation of the tentacle particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play, which is "explosion" in this case.
*   **`filename`**: The path to the sprite sheet containing the animation frames.
*   **`offset_x`**: Horizontal offset for the sprite's origin.
*   **`offset_y`**: Vertical offset for the sprite's origin.

### Animation: `explosion`

This section details the parameters for the "explosion" animation.

#### Key Attributes:

*   **`name`**: The name of this animation ("explosion").
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame.
*   **`frame_height`**: The height of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`pos_x`**: The starting X coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: The starting Y coordinate of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel.