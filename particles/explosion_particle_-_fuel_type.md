---
title: Explosion Particle - Fuel Type
category: particles
---

---

# Explosion Particle - Fuel Type

This document describes the configuration for a specific explosion particle effect in Noita, likely intended for use with fuel-related explosions.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`default_animation`**: "explosion" - Specifies the default animation to play.
*   **`filename`**: "data/particles/explosion_025_fuel.png" - The image file containing the sprite frames.
*   **`offset_x`**: "12.5" - Horizontal offset for the sprite.
*   **`offset_y`**: "12.5" - Vertical offset for the sprite.

## Animation Details

The `<RectAnimation>` element defines how the sprite frames are arranged and animated.

### Key Attributes:

*   **`name`**: "explosion" - The name of this animation, referenced by `default_animation`.
*   **`frame_count`**: "9" - The total number of frames in the animation.
*   **`frame_width`**: "26" - The width of each individual frame.
*   **`frame_height`**: "26" - The height of each individual frame.
*   **`frames_per_row`**: "8" - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: "0.03" - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: "0" - Indicates that the animation does not loop (plays once).
*   **`pos_x`**: "0" - Starting X position of the animation frames within the sprite sheet.
*   **`pos_y`**: "1" - Starting Y position of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: "1" - A flag that causes each frame to shrink by one pixel after being displayed.