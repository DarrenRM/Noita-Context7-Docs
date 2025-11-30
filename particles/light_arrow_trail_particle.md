---
title: Light Arrow Trail Particle
category: particles
---

---

# Light Arrow Trail Particle

This document describes the configuration for the `light_arrow_trail.xml` particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: Specifies the texture file for the particle sprite.
    *   `data/particles/light_arrow_trail.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `4.5`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `2.5`

### Animation: `stand`

The `RectAnimation` element defines the animation sequence.

#### Key Attributes:

*   **`name`**: The name of the animation.
    *   `stand`
*   **`frame_count`**: Total number of frames in the animation.
    *   `4`
*   **`frame_width`**: Width of each frame.
    *   `10`
*   **`frame_height`**: Height of each frame.
    *   `6`
*   **`frames_per_row`**: Number of frames in a single row of the sprite sheet.
    *   `4`
*   **`frame_wait`**: Time in seconds between frames.
    *   `0.01`
*   **`loop`**: Whether the animation should loop.
    *   `0` (False)
*   **`shrink_by_one_pixel`**: Whether to shrink the sprite by one pixel per frame.
    *   `1` (True)
*   **`pos_x`**: Starting X position for the animation frames on the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position for the animation frames on the sprite sheet.
    *   `1`