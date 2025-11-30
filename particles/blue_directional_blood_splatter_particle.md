---
title: Blue Directional Blood Splatter Particle
category: particles
---

# Blue Directional Blood Splatter Particle

This document describes the configuration for a blue directional blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual component of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: Specifies the texture file for the particle sprite.
    *   `data/particles/bloodsplatters/bloodsplatter_directional_blue_2.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `8`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `8`
*   **`default_animation`**: The name of the default animation to play.
    *   `smoke`

## Animation Details

The particle utilizes a rectangular animation sequence.

### Key Attributes for `RectAnimation` (named "smoke"):

*   **`name`**: The identifier for this animation.
    *   `smoke`
*   **`pos_x`**: Starting X position within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `5`
*   **`frame_width`**: The width of each individual frame.
    *   `32`
*   **`frame_height`**: The height of each individual frame.
    *   `16`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed.
    *   `0.025`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `8`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`