---
title: Light Bullet Sprite
category: projectiles_gfx
---

# Light Bullet Sprite

This document describes the sprite definition for the "light_bullet" projectile in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual appearance and animation of the projectile.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play. Here, it's set to `"fireball"`.
*   **`filename`**: The path to the image file containing the sprite's graphics.
    *   `data/projectiles_gfx/light_bullet.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `0.5` (Centered horizontally)
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `0.5` (Centered vertically)

## RectAnimation Definition

The `<RectAnimation>` tag defines a specific animation sequence using a rectangular grid of frames within the sprite sheet.

### Key Attributes:

*   **`name`**: The identifier for this animation sequence.
    *   `"fireball"`
*   **`frame_count`**: The total number of frames in this animation.
    *   `1`
*   **`frame_width`**: The width of each individual frame in pixels.
    *   `5`
*   **`frame_height`**: The height of each individual frame in pixels.
    *   `2`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.2`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `4`
*   **`loop`**: Whether the animation should loop.
    *   `0` (Does not loop)
*   **`pos_x`**: The starting X-coordinate (in frames) of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: The starting Y-coordinate (in frames) of the animation frames within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should be shrunk by one pixel.
    *   `1` (Shrinks by one pixel)