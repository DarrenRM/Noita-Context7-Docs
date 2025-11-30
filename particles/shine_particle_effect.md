---
title: Shine Particle Effect
category: particles
---

# Shine Particle Effect

This document describes the configuration for a simple shine particle effect in Noita, primarily focusing on its visual representation and animation.

## Sprite Configuration

The `Sprite` element defines the visual asset and its initial properties.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the particle.
    *   `data/particles/shine_01.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `4.5`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `4.5`
*   **`default_animation`**: The name of the animation to play by default.
    *   `explosion`

## Animation Definition

The `RectAnimation` element defines how the sprite is animated.

### Key Attributes:

*   **`name`**: The identifier for this animation, referenced by `default_animation`.
    *   `explosion`
*   **`pos_x`**: Starting X position within the sprite sheet for the animation.
    *   `0`
*   **`pos_y`**: Starting Y position within the sprite sheet for the animation.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `4`
*   **`frame_width`**: The width of each individual frame.
    *   `9`
*   **`frame_height`**: The height of each individual frame.
    *   `9`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.03`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `4`
*   **`loop`**: Determines if the animation should loop.
    *   `1` (loops)