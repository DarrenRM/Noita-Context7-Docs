---
title: Slow Bullet Sprite
category: projectiles_gfx
---

# Slow Bullet Sprite

This document describes the graphical assets for the "slow_bullet" projectile in Noita, focusing on its sprite and animation.

## Sprite Definition

The primary sprite definition for the slow bullet.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/slow_bullet.png` - The path to the image file containing the projectile's graphics.
*   **`default_animation`**: `fireball` - Specifies the default animation to be used for this sprite.
*   **`offset_x`**: `5` - Horizontal offset for the sprite's position.
*   **`offset_y`**: `5` - Vertical offset for the sprite's position.

## Animation: `fireball`

Details of the `fireball` animation used by the `slow_bullet` sprite.

### Key Attributes:

*   **`name`**: `fireball` - The name of this animation.
*   **`frame_count`**: `5` - The total number of frames in the animation.
*   **`frame_width`**: `11` - The width of each individual frame in pixels.
*   **`frame_height`**: `11` - The height of each individual frame in pixels.
*   **`frames_per_row`**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.09` - The duration (in seconds) each frame is displayed before advancing to the next.
*   **`pos_x`**: `0` - The starting X coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The starting Y coordinate of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - Indicates that each frame should be shrunk by one pixel.