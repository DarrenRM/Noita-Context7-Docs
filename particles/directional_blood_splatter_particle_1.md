---
title: Directional Blood Splatter Particle 1
category: particles
---

# Directional Blood Splatter Particle 1

This documentation describes the configuration for a directional blood splatter particle effect in Noita, specifically `bloodsplatter_directional_1.xml`.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: Specifies the texture file for the sprite.
    *   `data/particles/bloodsplatters/bloodsplatter_directional_1.png`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   `8`
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   `8`
*   **`default_animation`**: The name of the default animation to play.
    *   `smoke`

## Animation Configuration

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **`name`**: The name of the animation, referenced by `default_animation`.
    *   `smoke`
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `5`
*   **`frame_width`**: The width of each individual animation frame.
    *   `32`
*   **`frame_height`**: The height of each individual animation frame.
    *   `16`
*   **`frame_wait`**: The time in seconds to wait between frames.
    *   `0.025`
*   **`frames_per_row`**: The number of frames that fit horizontally in a single row of the sprite sheet.
    *   `8`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`