---
title: Big Smoke Cloud Particle
category: particles
---

---

# Big Smoke Cloud Particle

This document describes the configuration for a large smoke cloud particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`default_animation`**: Specifies the default animation to play. Here, it's set to `"explosion"`.
*   **`filename`**: The path to the sprite sheet containing the particle's frames.
    *   `data/particles/smoke_cloud_big.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `12`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `12`

## Animation Details

The `<RectAnimation>` tag defines how the sprite frames are sequenced to create the animation.

### Key Attributes:

*   **`name`**: The name of this animation, referenced by `default_animation`.
    *   `"explosion"`
*   **`frame_count`**: The total number of frames in the animation.
    *   `12`
*   **`frame_width`**: The width of each individual frame.
    *   `25`
*   **`frame_height`**: The height of each individual frame.
    *   `25`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `12`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.045`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`
*   **`pos_x`**: X-coordinate of the top-left corner of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: If set to `1`, each frame will shrink by one pixel on each side after each animation cycle (useful for fading effects).
    *   `1`