---
title: Large Fire Particle
category: particles
---

# Large Fire Particle

This document describes the configuration for the "large fire" particle effect in Noita, primarily focusing on its visual representation and animation.

## Sprite Configuration

The `Sprite` element defines the visual asset used for the particle.

### Key Attributes:

*   **`filename`**: Specifies the texture file for the particle sprite.
    *   `data/particles/fire_large.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `12`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `12`
*   **`default_animation`**: The name of the animation to play by default.
    *   `explosion`

## Animation: Explosion

The `RectAnimation` element defines the "explosion" animation sequence.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `explosion`
*   **`pos_x`**: Starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position of the animation frames within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `7`
*   **`frame_width`**: The width of each individual animation frame.
    *   `24`
*   **`frame_height`**: The height of each individual animation frame.
    *   `24`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.05`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `7`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`