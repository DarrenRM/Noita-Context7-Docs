---
title: Oil Blood Splatter Particle
category: particles
---

# Oil Blood Splatter Particle

This document describes the configuration for a specific blood splatter particle effect in Noita, named `bloodsplatter_oil_2`. This particle is designed to visually represent an oil-based blood splatter.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_oil_2.png`
    *   Specifies the image file used for the particle's texture.
*   **`offset_x`**: `8`
    *   Horizontal offset for the sprite's origin.
*   **`offset_y`**: `8`
    *   Vertical offset for the sprite's origin.
*   **`default_animation`**: `smoke`
    *   The name of the default animation to play when the particle is spawned.

## Animation Details: `smoke`

The `smoke` animation defines how the sprite is displayed over time, including its frames and timing.

### Key Attributes:

*   **`name`**: `smoke`
    *   The identifier for this animation.
*   **`frame_count`**: `4`
    *   The total number of frames in the animation.
*   **`frame_width`**: `17`
    *   The width of each individual frame in pixels.
*   **`frame_height`**: `17`
    *   The height of each individual frame in pixels.
*   **`frames_per_row`**: `8`
    *   Indicates how many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.025`
    *   The duration (in seconds) each frame is displayed before advancing to the next.
*   **`loop`**: `0`
    *   Specifies that the animation does not loop (plays only once).
*   **`shrink_by_one_pixel`**: `1`
    *   Enables a visual effect where the sprite shrinks by one pixel per frame.
*   **`pos_x`**: `0`
    *   The starting X-coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: `1`
    *   The starting Y-coordinate of the animation frames within the sprite sheet.