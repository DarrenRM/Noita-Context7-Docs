---
title: Tiny Grey Smoke Cloud Particle
category: particles
---

# Tiny Grey Smoke Cloud Particle

This document describes the configuration for a small, grey smoke cloud particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The particle uses a sprite sheet to define its visual appearance and animation.

### Key Attributes:

*   **`filename`**: `data/particles/smoke_cloud_grey_4.png` - Specifies the texture file for the particle.
*   **`offset_x`**: `10` - Horizontal offset for the sprite.
*   **`offset_y`**: `10` - Vertical offset for the sprite.
*   **`default_animation`**: `explosion` - The name of the animation to play by default.

## Animation Details

The particle utilizes a rectangular animation sequence.

### Key Attributes:

*   **`name`**: `explosion` - The identifier for this animation.
*   **`pos_x`**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **`pos_y`**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **`frame_count`**: `8` - The total number of frames in the animation.
*   **`frame_width`**: `20` - The width of each individual animation frame.
*   **`frame_height`**: `20` - The height of each individual animation frame.
*   **`frame_wait`**: `0.09` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays once).