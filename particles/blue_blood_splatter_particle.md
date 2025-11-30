---
title: Blue Blood Splatter Particle
category: particles
---

# Blue Blood Splatter Particle

This document describes the configuration for a blue blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_blue_2.png`
    *   Specifies the texture file used for the sprite.
*   **`offset_x`**: `8`
    *   Horizontal offset for the sprite's origin.
*   **`offset_y`**: `8`
    *   Vertical offset for the sprite's origin.

## Animation Details

The particle utilizes a `RectAnimation` to define its visual sequence.

### Key Attributes:

*   **`name`**: `smoke`
    *   The internal name for this animation.
*   **`frame_count`**: `4`
    *   Total number of frames in the animation.
*   **`frame_width`**: `17`
    *   Width of each individual frame.
*   **`frame_height`**: `17`
    *   Height of each individual frame.
*   **`frames_per_row`**: `8`
    *   Number of frames arranged horizontally in the texture atlas.
*   **`frame_wait`**: `0.025`
    *   Duration (in seconds) each frame is displayed before transitioning to the next.
*   **`loop`**: `0`
    *   Indicates that the animation does not loop (plays once).
*   **`shrink_by_one_pixel`**: `1`
    *   Enables a one-pixel shrink effect per frame, often used for fading or shrinking effects.
*   **`pos_x`**: `0`
    *   X-coordinate of the top-left corner of the animation's frame region within the sprite sheet.
*   **`pos_y`**: `1`
    *   Y-coordinate of the top-left corner of the animation's frame region within the sprite sheet.