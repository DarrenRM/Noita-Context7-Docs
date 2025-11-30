---
title: Tiny Red Smoke Cloud Particle
category: particles
---

# Tiny Red Smoke Cloud Particle

This document describes the configuration for a small, red smoke cloud particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/smoke_cloud_tiny_red_1.png`
    *   Specifies the image file used for the particle's visual representation.
*   **`offset_x`**: `10`
    *   Horizontal offset for the sprite.
*   **`offset_y`**: `10`
    *   Vertical offset for the sprite.
*   **`default_animation`**: `explosion`
    *   Sets the default animation to be played when the particle is spawned.

## Animation Details

The particle utilizes a `RectAnimation` for its visual sequence.

### Animation: `explosion`

*   **`name`**: `explosion`
    *   Identifies this specific animation.
*   **`pos_x`**: `0`
    *   X-coordinate of the animation's starting position within the sprite sheet.
*   **`pos_y`**: `0`
    *   Y-coordinate of the animation's starting position within the sprite sheet.
*   **`frame_count`**: `6`
    *   The total number of frames in this animation.
*   **`frame_width`**: `20`
    *   The width of each individual frame in pixels.
*   **`frame_height`**: `20`
    *   The height of each individual frame in pixels.
*   **`frame_wait`**: `0.06`
    *   The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: `6`
    *   Indicates how many frames are arranged horizontally in a single row of the sprite sheet.
*   **`loop`**: `0`
    *   Specifies that the animation should not loop (it plays once).