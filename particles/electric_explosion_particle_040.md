---
title: Electric Explosion Particle 040
category: particles
---

# Electric Explosion Particle 040

This document describes the configuration for a specific electric explosion particle effect in Noita, identified as `explosion_040_electric2.xml`.

## Sprite Configuration

The primary visual component of this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/explosion_040_electric2.png` - Specifies the image file used for the particle's animation.
*   **`default_animation`**: `explosion` - Sets the default animation to be played.
*   **`offset_x`**: `20` - Horizontal offset for the sprite.
*   **`offset_y`**: `20` - Vertical offset for the sprite.

## Animation Details

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **`name`**: `explosion` - The name of this animation, referenced by `default_animation`.
*   **`frame_count`**: `7` - The total number of frames in the animation.
*   **`frame_width`**: `41` - The width of each individual frame.
*   **`frame_height`**: `41` - The height of each individual frame.
*   **`frames_per_row`**: `7` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays once).
*   **`pos_x`**: `0` - X-coordinate of the top-left corner of the animation within the sprite sheet.
*   **`pos_y`**: `1` - Y-coordinate of the top-left corner of the animation within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - A flag that causes each frame to shrink by one pixel after being displayed.