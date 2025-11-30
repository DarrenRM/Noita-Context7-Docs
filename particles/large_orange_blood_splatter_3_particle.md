---
title: Large Orange Blood Splatter 3 Particle
category: particles
---

---

# Large Orange Blood Splatter 3 Particle

This document describes the configuration for a specific particle effect in Noita, representing a large orange blood splatter.

## Sprite Configuration

The primary visual representation of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_large_orange_3.png` - Specifies the image file used for the sprite.
*   **`offset_x`**: `16` - The horizontal offset of the sprite's origin.
*   **`offset_y`**: `16` - The vertical offset of the sprite's origin.

## Animation Details

The particle utilizes a `RectAnimation` to define its visual sequence.

### Key Attributes:

*   **`name`**: `smoke` - The internal name for this animation sequence.
*   **`frame_count`**: `6` - The total number of frames in the animation.
*   **`frame_width`**: `33` - The width of each individual frame.
*   **`frame_height`**: `33` - The height of each individual frame.
*   **`frame_wait`**: `0.03` - The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: `8` - The number of frames arranged horizontally within the sprite sheet.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays only once).
*   **`shrink_by_one_pixel`**: `1` - Suggests a visual effect where the sprite shrinks by one pixel per frame.
*   **`pos_x`**: `0` - The starting X-coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The starting Y-coordinate of the animation frames within the sprite sheet.