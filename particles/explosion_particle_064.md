---
title: Explosion Particle 064
category: particles
---

---

# Explosion Particle 064

This document describes the configuration for a specific explosion particle effect in Noita, identified as `explosion_064`.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/explosion_064.png` - Specifies the image file used for the particle's visual representation.
*   **`offset_x`**: `32` - The horizontal offset of the sprite's origin.
*   **`offset_y`**: `32` - The vertical offset of the sprite's origin.

## Animation Configuration

The particle utilizes a rectangular animation sequence.

### Key Attributes:

*   **`name`**: `explosion` - The name of this animation sequence.
*   **`frame_count`**: `5` - The total number of frames in the animation.
*   **`frame_width`**: `65` - The width of each individual frame.
*   **`frame_height`**: `65` - The height of each individual frame.
*   **`frames_per_row`**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.06` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays only once).
*   **`shrink_by_one_pixel`**: `1` - A flag that causes the sprite to shrink by one pixel each frame, creating a fading or shrinking effect.
*   **`pos_x`**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The starting Y position of the animation frames within the sprite sheet.