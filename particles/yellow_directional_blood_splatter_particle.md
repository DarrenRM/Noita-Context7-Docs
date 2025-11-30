---
title: Yellow Directional Blood Splatter Particle
category: particles
---

# Yellow Directional Blood Splatter Particle

This document describes the configuration for a yellow directional blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual component of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: Specifies the texture file for the particle.
    *   `data/particles/bloodsplatters/bloodsplatter_directional_yellow_2.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `8`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `8`
*   **`default_animation`**: The name of the default animation to play.
    *   `smoke`

## Animation Definition

The particle utilizes a rectangular animation for its visual sequence.

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
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.025`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `8`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`

This configuration defines a short, non-looping animation of 5 frames, each 32x16 pixels, extracted from a sprite sheet where frames are arranged 8 per row. The animation plays quickly at 0.025 seconds per frame.