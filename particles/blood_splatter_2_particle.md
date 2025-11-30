---
title: Blood Splatter 2 Particle
category: particles
---

---

# Blood Splatter 2 Particle

This document describes the configuration for `bloodsplatter_2.xml`, a particle effect in Noita.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_2.png` - Specifies the texture file used for the particle.
*   **`offset_x`**: `8` - Horizontal offset for the sprite.
*   **`offset_y`**: `8` - Vertical offset for the sprite.

## Animation Configuration

The particle utilizes a `RectAnimation` for its visual sequence.

### Key Attributes:

*   **`name`**: `smoke` - The name of this animation.
*   **`frame_count`**: `4` - The total number of frames in the animation.
*   **`frame_width`**: `17` - The width of each individual frame.
*   **`frame_height`**: `17` - The height of each individual frame.
*   **`frames_per_row`**: `8` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.025` - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays once).
*   **`shrink_by_one_pixel`**: `1` - Suggests a visual effect where the sprite shrinks by one pixel per frame.
*   **`pos_x`**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The starting Y position of the animation frames within the sprite sheet.