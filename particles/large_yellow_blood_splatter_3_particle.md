---
title: Large Yellow Blood Splatter 3 Particle
category: particles
---

# Large Yellow Blood Splatter 3 Particle

This document describes the configuration for a specific blood splatter particle effect in Noita, identified as `bloodsplatter_large_yellow_3`. This particle is used to visually represent a large, yellow blood splatter.

## Sprite Configuration

The primary visual representation of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_large_yellow_3.png`
    *   Specifies the image file used for the particle's texture.
*   **`offset_x`**: `16`
    *   The horizontal offset of the sprite's origin.
*   **`offset_y`**: `16`
    *   The vertical offset of the sprite's origin.
*   **`default_animation`**: `smoke`
    *   The name of the default animation to play when the particle is spawned.

## Animation Details

The particle utilizes a rectangular animation sequence for its visual effect.

### Animation Name: `smoke`

This animation defines how the sprite frames are sequenced to create the visual effect.

#### Key Attributes:

*   **`name`**: `smoke`
    *   The identifier for this animation sequence.
*   **`frame_count`**: `6`
    *   The total number of frames in the animation.
*   **`frame_width`**: `33`
    *   The width of each individual frame in pixels.
*   **`frame_height`**: `33`
    *   The height of each individual frame in pixels.
*   **`frames_per_row`**: `8`
    *   The number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.03`
    *   The duration (in seconds) each frame is displayed before advancing to the next.
*   **`loop`**: `0`
    *   Indicates that the animation does not loop (plays only once).
*   **`pos_x`**: `0`
    *   The starting X-coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: `1`
    *   The starting Y-coordinate of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1`
    *   A flag indicating that each frame should shrink by one pixel after being displayed.