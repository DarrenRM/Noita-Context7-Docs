---
title: Small Explosion Flare Particle
category: particles
---

# Small Explosion Flare Particle

This document describes the configuration for a small explosion flare particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play.
    *   Value: `"explosion"`
*   **`filename`**: The path to the sprite sheet containing the particle's frames.
    *   Value: `"data/particles/explosion_flare_small.png"`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   Value: `"8"`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   Value: `"8"`

## RectAnimation: "explosion"

This element defines a rectangular animation sequence for the particle.

### Key Attributes:

*   **`name`**: The name of this animation, referenced by `default_animation`.
    *   Value: `"explosion"`
*   **`frame_count`**: The total number of frames in the animation.
    *   Value: `"3"`
*   **`frame_width`**: The width of each individual frame.
    *   Value: `"17"`
*   **`frame_height`**: The height of each individual frame.
    *   Value: `"17"`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   Value: `"3"`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   Value: `"0.05"`
*   **`loop`**: Determines if the animation should loop. `0` means no loop.
    *   Value: `"0"`
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet.
    *   Value: `"0"`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet.
    *   Value: `"1"`
*   **`shrink_by_one_pixel`**: Whether to shrink the sprite by one pixel per frame.
    *   Value: `"1"`