---
title: Gas Bubble Particle
category: particles
---

# Gas Bubble Particle

This document describes the `gas_bubble_01.xml` particle definition, used for creating gas bubble effects in Noita.

## Sprite Definition

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: `data/particles/gas_bubble_01.png` - Specifies the texture file used for the sprite.
*   **`default_animation`**: `bubble` - Sets the default animation to play.
*   **`offset_x`**: `1.5` - Horizontal offset for the sprite.
*   **`offset_y`**: `1.5` - Vertical offset for the sprite.

## Animation: `bubble`

The `RectAnimation` element defines the specific animation sequence for the bubble.

### Key Attributes:

*   **`name`**: `bubble` - The name of this animation.
*   **`frame_count`**: `2` - The total number of frames in the animation.
*   **`frame_width`**: `4` - The width of each frame in pixels.
*   **`frame_height`**: `4` - The height of each frame in pixels.
*   **`frames_per_row`**: `2` - How many frames are arranged horizontally in the texture.
*   **`frame_wait`**: `0.25` - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays once).
*   **`pos_x`**: `0` - The starting X position of the animation frames within the texture.
*   **`pos_y`**: `1` - The starting Y position of the animation frames within the texture.
*   **`shrink_by_one_pixel`**: `1` - A flag indicating if the sprite should shrink by one pixel per frame.