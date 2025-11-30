---
title: Big Red Smoke Cloud Particle
category: particles
---

# Big Red Smoke Cloud Particle

This document describes the configuration for a "Big Red Smoke Cloud" particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The particle uses a sprite sheet for its visual representation.

### Sprite Attributes

*   **`default_animation`**: `explosion` - Specifies the default animation to play.
*   **`filename`**: `data/particles/smoke_cloud_big_red.png` - The path to the sprite sheet image.
*   **`offset_x`**: `12` - Horizontal offset for the sprite.
*   **`offset_y`**: `12` - Vertical offset for the sprite.

### Animation: `explosion`

This animation defines how the sprite sheet is used to create the smoke cloud effect.

*   **`name`**: `explosion` - The name of this animation.
*   **`frame_count`**: `12` - The total number of frames in the animation.
*   **`frame_width`**: `25` - The width of each individual frame.
*   **`frame_height`**: `25` - The height of each individual frame.
*   **`frames_per_row`**: `12` - The number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.045` - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays once).
*   **`pos_x`**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The starting Y position of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - A flag that causes each frame to shrink by one pixel after being displayed.