---
title: Directional Blood Splatter 2 Particle
category: particles
---

# Directional Blood Splatter 2 Particle

This document describes the configuration for a directional blood splatter particle effect in Noita, specifically `bloodsplatter_directional_2.xml`.

## Sprite Configuration

The primary visual component of this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: Specifies the image file used for the particle sprite.
    *   `data/particles/bloodsplatters/bloodsplatter_directional_2.png`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   `8`
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   `8`
*   **`default_animation`**: The name of the default animation to play.
    *   `smoke`

## Animation Configuration

The particle utilizes a rectangular animation for its visual sequence.

### Key Attributes for `RectAnimation` (named "smoke"):

*   **`name`**: The identifier for this animation.
    *   `smoke`
*   **`pos_x`**: The X-coordinate of the animation's top-left corner within the sprite sheet.
    *   `0`
*   **`pos_y`**: The Y-coordinate of the animation's top-left corner within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `5`
*   **`frame_width`**: The width of each individual frame.
    *   `32`
*   **`frame_height`**: The height of each individual frame.
    *   `16`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.025`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `8`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`