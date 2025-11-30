---
title: Levitation Projectile Sprite
category: projectiles_gfx
---

# Levitation Projectile Sprite

This document describes the sprite definition for the "levitation" projectile in Noita. It details the visual appearance and animation of this projectile.

## Sprite Definition

The main `Sprite` element defines the base visual properties and the primary animation.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/levitation.png` - Specifies the image file used for the sprite.
*   **`default_animation`**: `fireball` - Sets the animation to play by default.
*   **`offset_x`**: `2.5` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `2.5` - Vertical offset for the sprite's origin.

## RectAnimation: "fireball"

This section defines a specific rectangular animation named "fireball".

### Key Attributes:

*   **`name`**: `fireball` - The identifier for this animation.
*   **`frame_count`**: `4` - The total number of frames in the animation.
*   **`frame_width`**: `6` - The width of each individual frame in pixels.
*   **`frame_height`**: `6` - The height of each individual frame in pixels.
*   **`frames_per_row`**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.05` - The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**: `0` - The starting X-coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The starting Y-coordinate of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - Indicates that each frame should be shrunk by one pixel.