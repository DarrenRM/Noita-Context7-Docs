---
title: Large Purple Blood Splatter Particle
category: particles
---

# Large Purple Blood Splatter Particle

This document describes the configuration for a large purple blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_large_purple_1.png`
    *   Specifies the texture file used for the particle.
*   **`offset_x`**: `16`
    *   Horizontal offset for the sprite's origin.
*   **`offset_y`**: `16`
    *   Vertical offset for the sprite's origin.
*   **`default_animation`**: `smoke`
    *   The name of the animation to play by default.

## Animation Details

The `RectAnimation` element defines the specific animation sequence for the particle.

### Key Attributes:

*   **`name`**: `smoke`
    *   The identifier for this animation.
*   **`frame_count`**: `6`
    *   The total number of frames in the animation.
*   **`frame_width`**: `33`
    *   The width of each individual frame in pixels.
*   **`frame_height`**: `33`
    *   The height of each individual frame in pixels.
*   **`frames_per_row`**: `8`
    *   The number of frames arranged horizontally in the texture atlas.
*   **`frame_wait`**: `0.03`
    *   The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0`
    *   Indicates if the animation should loop. `0` means it does not loop (plays once).
*   **`shrink_by_one_pixel`**: `1`
    *   When set to `1`, each frame will shrink by one pixel on each side after each animation cycle.

### Animation Position:

*   **`pos_x`**: `0`
    *   The X-coordinate of the top-left corner of the animation frames within the texture atlas.
*   **`pos_y`**: `1`
    *   The Y-coordinate of the top-left corner of the animation frames within the texture atlas.