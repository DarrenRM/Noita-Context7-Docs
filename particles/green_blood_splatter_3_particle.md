---
title: Green Blood Splatter 3 Particle
category: particles
---

# Green Blood Splatter 3 Particle

This document describes the configuration for a specific particle effect in Noita, representing a green blood splatter.

## Sprite Configuration

The primary visual representation of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: Specifies the image file used for the sprite.
    *   `data/particles/bloodsplatters/bloodsplatter_green_3.png`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   `8`
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   `8`
*   **`default_animation`**: The name of the animation to be used by default.
    *   `smoke`

## Animation Details

The particle utilizes a rectangular animation for its visual sequence.

### Key Attributes for `RectAnimation` (named "smoke"):

*   **`name`**: The identifier for this animation.
    *   `smoke`
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `4`
*   **`frame_width`**: The width of each individual animation frame.
    *   `16`
*   **`frame_height`**: The height of each individual animation frame.
    *   `16`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.025`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `8`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`