---
title: Large Oil Blood Splatter Particle
category: particles
---

---

# Large Oil Blood Splatter Particle

This document describes the configuration for a large oil blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`default_animation`**: Specifies the default animation to play.
    *   Value: `"smoke"`
*   **`filename`**: The path to the sprite sheet containing the animation frames.
    *   Value: `"data/particles/bloodsplatters/bloodsplatter_large_oil_1.png"`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   Value: `"16"`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   Value: `"16"`

## Animation Details

The `<RectAnimation>` element defines the specific animation sequence used by the sprite.

### Key Attributes:

*   **`name`**: The name of this animation, referenced by `default_animation`.
    *   Value: `"smoke"`
*   **`frame_count`**: The total number of frames in the animation.
    *   Value: `"6"`
*   **`frame_width`**: The width of each individual frame in pixels.
    *   Value: `"33"`
*   **`frame_height`**: The height of each individual frame in pixels.
    *   Value: `"33"`
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
    *   Value: `"8"`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   Value: `"0.03"`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   Value: `"0"`
*   **`pos_x`**: The starting X-coordinate of the animation frames on the sprite sheet.
    *   Value: `"0"`
*   **`pos_y`**: The starting Y-coordinate of the animation frames on the sprite sheet.
    *   Value: `"1"`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel each step.
    *   Value: `"1"`

This particle effect is designed to visually represent a large oil-based blood splatter, likely with a short, non-looping animation.