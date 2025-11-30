---
title: Large Blood Splatter Particle
category: particles
---

# Large Blood Splatter Particle

This document describes the configuration for a large blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_large_1.png` - Specifies the image file used for the particle's visual representation.
*   **`offset_x`**: `16` - The horizontal offset of the sprite's origin.
*   **`offset_y`**: `16` - The vertical offset of the sprite's origin.
*   **`default_animation`**: `"smoke"` - The name of the default animation to play when the particle is spawned.

## Animation Details

The particle utilizes a `RectAnimation` to define its animation sequence.

### Key Attributes:

*   **`name`**: `"smoke"` - The identifier for this specific animation.
*   **`frame_count`**: `6` - The total number of frames in the animation.
*   **`frame_width`**: `33` - The width of each individual frame in pixels.
*   **`frame_height`**: `33` - The height of each individual frame in pixels.
*   **`frames_per_row`**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.03` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`loop`**: `0` - Indicates that the animation does not loop (it plays once).
*   **`shrink_by_one_pixel`**: `1` - A flag that suggests frames might shrink by one pixel, potentially for visual effect or optimization.
*   **`pos_x`**: `0` - The horizontal starting position of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The vertical starting position of the animation frames within the sprite sheet.