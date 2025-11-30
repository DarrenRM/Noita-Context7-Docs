---
title: Electric Explosion Particle
category: particles
---

# Electric Explosion Particle

This document describes the configuration for an electric explosion particle effect in Noita, as defined in `explosion_016_electric.xml`.

## Sprite Configuration

The primary visual component of the particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/explosion_016_electric.png` - Specifies the image file used for the particle's animation.
*   **`offset_x`**: `8` - Horizontal offset for the sprite.
*   **`offset_y`**: `8` - Vertical offset for the sprite.
*   **`default_animation`**: `explosion` - The name of the animation to play by default.

## Animation Details

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **`name`**: `explosion` - The identifier for this animation.
*   **`pos_x`**: `0` - Starting X position within the sprite sheet.
*   **`pos_y`**: `0` - Starting Y position within the sprite sheet.
*   **`frame_count`**: `7` - The total number of frames in the animation.
*   **`frame_width`**: `16` - The width of each individual frame.
*   **`frame_height`**: `16` - The height of each individual frame.
*   **`frame_wait`**: `0.04` - The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays only once).