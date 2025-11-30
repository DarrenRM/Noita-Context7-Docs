---
title: Explosion Flare Particle
category: particles
---

---

# Explosion Flare Particle

This document describes the configuration for the "explosion_flare" particle effect in Noita, used to create visual flair for explosions.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play, which is "explosion" in this case.
*   **`filename`**: The path to the sprite sheet containing the particle's frames.
*   **`offset_x`**, **`offset_y`**: The pixel offset of the sprite's origin.

## RectAnimation Configuration

The `RectAnimation` element defines the specific animation sequence for the "explosion" state.

### Key Attributes:

*   **`name`**: The name of this animation, matching `default_animation` in the `Sprite` tag.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: The dimensions of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: Whether the animation should loop (0 for no, 1 for yes).
*   **`pos_x`**, **`pos_y`**: The starting position of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: A flag to indicate if frames should be shrunk by one pixel, often used for certain sprite effects.