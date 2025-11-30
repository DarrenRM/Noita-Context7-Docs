---
title: Large Green Bloodsplatter 3 Particle
category: particles
---

---

# Large Green Bloodsplatter 3 Particle

This document describes the configuration for a large green bloodsplatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`default_animation`**: Specifies the default animation to play, which is "smoke" in this case.
*   **`filename`**: The path to the sprite sheet containing the animation frames.
    *   `data/particles/bloodsplatters/bloodsplatter_large_green_3.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `16`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `16`

## Animation Details

The `<RectAnimation>` element defines the specific animation sequence.

### Key Attributes:

*   **`name`**: The name of the animation, matching `default_animation`.
    *   `smoke`
*   **`frame_count`**: The total number of frames in the animation.
    *   `6`
*   **`frame_width`**: The width of each individual frame.
    *   `33`
*   **`frame_height`**: The height of each individual frame.
    *   `33`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `8`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.03`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`
*   **`pos_x`**: Starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position of the animation frames within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: Whether each frame should shrink by one pixel after each animation cycle. `1` enables this.
    *   `1`