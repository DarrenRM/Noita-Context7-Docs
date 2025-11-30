---
title: Green Directional Blood Splatter Particle
category: particles
---

# Green Directional Blood Splatter Particle

This document describes the configuration for a green directional blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual component of this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the particle.
    *   `data/particles/bloodsplatters/bloodsplatter_directional_green_2.png`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   `8`
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   `8`
*   **`default_animation`**: The name of the default animation to play.
    *   `smoke`

## Animation Details

The particle utilizes a `RectAnimation` for its visual sequence.

### Key Attributes:

*   **`name`**: The identifier for this animation.
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
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `8`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`