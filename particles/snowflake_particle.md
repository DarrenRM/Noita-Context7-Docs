---
title: Snowflake Particle
category: particles
---

---

# Snowflake Particle

This document describes the configuration for a snowflake particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual representation of the snowflake is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: Specifies the image file used for the particle.
    *   `data/particles/snowflake_1.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `4`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `4`
*   **`default_animation`**: The animation to play by default.
    *   `explosion`

## Animation Details

The particle utilizes a simple animation defined by `<RectAnimation>`.

### Key Attributes:

*   **`name`**: The name of this animation.
    *   `explosion`
*   **`pos_x`**: Starting X position within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `1`
*   **`frame_width`**: The width of each individual frame.
    *   `8`
*   **`frame_height`**: The height of each individual frame.
    *   `8`
*   **`frame_wait`**: The time in seconds to wait between frames.
    *   `0.03`
*   **`frames_per_row`**: How many frames are present in a single row of the sprite sheet.
    *   `3`
*   **`loop`**: Whether the animation should loop.
    *   `0` (False)