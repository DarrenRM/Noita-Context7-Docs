---
title: Shine Levitation Particle
category: particles
---

---

# Shine Levitation Particle

This document describes the configuration for the "shine_levitation" particle effect in Noita, primarily focusing on its visual representation and animation.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play. In this case, it's "explosion".
*   **`filename`**: The path to the sprite sheet used for the particle's animation.
    *   `data/particles/shine_levitation.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `2.5`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `2.5`

## RectAnimation: "explosion"

The `RectAnimation` element defines the specific animation sequence for the "explosion" state.

### Key Attributes:

*   **`name`**: The name of this animation sequence.
    *   `explosion`
*   **`frame_count`**: The total number of frames in the animation.
    *   `3`
*   **`frame_width`**: The width of each individual frame in pixels.
    *   `6`
*   **`frame_height`**: The height of each individual frame in pixels.
    *   `6`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `3`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.08`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping (it plays once).
    *   `0`
*   **`shrink_by_one_pixel`**: If set to `1`, the particle will shrink by one pixel each frame.
    *   `1`
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet (in grid units).
    *   `0`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet (in grid units).
    *   `1`