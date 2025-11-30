---
title: Looping Spark Particle
category: particles
---

# Looping Spark Particle

This documentation describes the configuration for a looping spark particle effect in Noita, designed for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the particle.
    *   `data/particles/spark_particle.png`
*   **`offset_x`**, **`offset_y`**: Adjusts the particle's pivot point.
    *   `4.5`
    *   `4.5`
*   **`default_animation`**: Sets the initial animation to play.
    *   `explosion`

## Animation Definition

The `RectAnimation` element defines the specific animation sequence for the particle.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `explosion`
*   **`pos_x`**, **`pos_y`**: The top-left corner of the animation frame within the sprite sheet.
    *   `0`
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `3`
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
    *   `9`
    *   `9`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.08`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `3`
*   **`loop`**: Determines if the animation should repeat.
    *   `1` (meaning loop indefinitely)