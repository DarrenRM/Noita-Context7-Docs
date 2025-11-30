---
title: Orange Blood Splatter 2 Particle
category: particles
---

# Orange Blood Splatter 2 Particle

This document describes the configuration for a specific blood splatter particle effect in Noita, identified as `bloodsplatter_orange_2`.

## Sprite Configuration

The primary visual representation of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_orange_2.png` - Specifies the image file used for the sprite.
*   **`offset_x`**: `8` - The horizontal offset of the sprite's origin.
*   **`offset_y`**: `8` - The vertical offset of the sprite's origin.
*   **`default_animation`**: `smoke` - The name of the default animation to play.

## Animation Details

The `<RectAnimation>` element defines the animation sequence for the sprite.

### Key Attributes:

*   **`name`**: `smoke` - The identifier for this animation.
*   **`frame_count`**: `4` - The total number of frames in the animation.
*   **`frame_width`**: `17` - The width of each individual frame.
*   **`frame_height`**: `17` - The height of each individual frame.
*   **`frames_per_row`**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.025` - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays only once).
*   **`shrink_by_one_pixel`**: `1` - Suggests a visual effect where the sprite shrinks by one pixel per frame.
*   **`pos_x`**: `0` - The starting X-coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The starting Y-coordinate of the animation frames within the sprite sheet.