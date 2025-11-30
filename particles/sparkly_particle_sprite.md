---
title: Sparkly Particle Sprite
category: particles
---

# Sparkly Particle Sprite

This document describes the sprite definition for the "sparkly" particle effect in Noita.

## Sprite Definition

The primary `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: Specifies the image file used for the sprite.
    *   `data/particles/sparkly.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `6`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `6`
*   **`default_animation`**: The name of the animation to play by default.
    *   `explosion`

## Animation: `explosion`

This section details the `explosion` animation used by the sparkly particle.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `explosion`
*   **`pos_x`**: X-coordinate of the top-left corner of the animation frame within the sprite sheet.
    *   `0`
*   **`pos_y`**: Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `8`
*   **`frame_width`**: The width of each individual animation frame.
    *   `12`
*   **`frame_height`**: The height of each individual animation frame.
    *   `12`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.05`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `8`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`