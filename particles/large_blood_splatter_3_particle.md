---
title: Large Blood Splatter 3 Particle
category: particles
---

# Large Blood Splatter 3 Particle

This document describes the configuration for a large blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_large_3.png`
    *   Specifies the image file used for the particle's visual representation.
*   **`offset_x`**: `16`
    *   Horizontal offset for the sprite's origin.
*   **`offset_y`**: `16`
    *   Vertical offset for the sprite's origin.

## Animation Configuration

The particle utilizes a `<RectAnimation>` to define its animation sequence.

### Key Attributes:

*   **`name`**: `smoke`
    *   The name of this specific animation.
*   **`frame_count`**: `6`
    *   The total number of frames in the animation.
*   **`frame_width`**: `33`
    *   The width of each individual frame in pixels.
*   **`frame_height`**: `33`
    *   The height of each individual frame in pixels.
*   **`frames_per_row`**: `8`
    *   The number of frames arranged horizontally within the sprite sheet.
*   **`frame_wait`**: `0.03`
    *   The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`loop`**: `0`
    *   Indicates that the animation does not loop (plays only once).
*   **`shrink_by_one_pixel`**: `1`
    *   Enables a visual effect where the sprite shrinks by one pixel per frame.