---
title: Gunpowder Smoke Particle 04
category: particles
---

# Gunpowder Smoke Particle 04

This document describes the configuration for a specific gunpowder smoke particle effect in Noita, designed for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the default animation to play. Here, it's set to "explosion".
*   **`filename`**: The path to the sprite sheet containing the particle's frames.
    *   `data/particles/smoke_gunpowder_04.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `10`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `10`
*   **`rect_animation`**: References a `RectAnimation` element by name.

## RectAnimation Configuration

The `RectAnimation` element defines the details of a rectangular sprite sheet animation.

### Key Attributes:

*   **`frame_count`**: The total number of frames in the animation.
    *   `9`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.09`
*   **`frame_height`**: The height of a single frame in pixels.
    *   `20`
*   **`frame_width`**: The width of a single frame in pixels.
    *   `20`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `12`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`
*   **`name`**: The name of the animation, referenced by the `Sprite` element.
    *   `explosion`
*   **`pos_x`**: The starting X-coordinate of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: The starting Y-coordinate of the animation frames within the sprite sheet.
    *   `0`

This particle effect is designed to be a short, non-looping explosion animation, likely used for visual feedback when gunpowder-related events occur.