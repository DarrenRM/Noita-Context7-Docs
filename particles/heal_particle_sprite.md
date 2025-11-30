---
title: Heal Particle Sprite
category: particles
---

# Heal Particle Sprite

This document describes the sprite configuration for the "heal" particle in Noita.

## Sprite Configuration

The primary sprite element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: `data/particles/heal.png` - Specifies the image file used for the particle's sprite.
*   **`offset_x`**: `3.5` - Horizontal offset for the sprite.
*   **`offset_y`**: `3.5` - Vertical offset for the sprite.

## Animation Details

The `RectAnimation` element defines how the sprite sheet is used to create an animation.

### Key Attributes:

*   **`name`**: `fireball` - The internal name for this animation sequence.
*   **`frame_count`**: `5` - The total number of frames in the animation.
*   **`frame_width`**: `8` - The width of each individual frame in pixels.
*   **`frame_height`**: `8` - The height of each individual frame in pixels.
*   **`frames_per_row`**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays once).
*   **`shrink_by_one_pixel`**: `1` - A flag that likely causes the sprite to shrink by one pixel each frame.