---
title: Protection All Evil Particle
category: particles
---

---

# Protection All Evil Particle

This document describes the `protection_all_evil.xml` particle file, used for visual effects in Noita.

## Sprite

The primary visual component of the particle.

### Key Attributes:

*   **`filename`**: `data/particles/protection_all_evil.png` - Specifies the image file used for the particle's animation.
*   **`offset_x`**: `3.5` - Horizontal offset for the sprite.
*   **`offset_y`**: `4` - Vertical offset for the sprite.

### Animations:

*   **`default_animation`**: `explosion` - The name of the animation to play by default.

## RectAnimation

Defines a rectangular animation sequence.

### Key Attributes:

*   **`name`**: `explosion` - The identifier for this animation.
*   **`frame_count`**: `1` - The total number of frames in the animation.
*   **`frame_width`**: `7` - The width of each individual frame.
*   **`frame_height`**: `8` - The height of each individual frame.
*   **`frames_per_row`**: `6` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.09` - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0` - Whether the animation should loop (0 for no, 1 for yes).
*   **`pos_x`**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **`pos_y`**: `0` - The starting Y position of the animation frames within the sprite sheet.