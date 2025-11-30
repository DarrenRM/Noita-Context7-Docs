---
title: Small Fireball Sprite
category: projectiles_gfx
---

# Small Fireball Sprite

This documentation describes the sprite definition for the "small fireball" projectile in Noita. It details the image file used, its positioning, and its animation properties.

## Sprite Definition

The core sprite definition is provided by the `<Sprite>` tag.

### Key Attributes

*   **`filename`**: Specifies the path to the sprite image file.
    *   `data/projectiles_gfx/fireball_small.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `2`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `2`
*   **`default_animation`**: The name of the animation to be used by default.
    *   `fireball`

## Animation Definition

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes

*   **`name`**: The identifier for this animation.
    *   `fireball`
*   **`pos_x`**: Starting X-coordinate of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y-coordinate of the animation frames within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `4`
*   **`frame_width`**: The width of each individual animation frame.
    *   `4`
*   **`frame_height`**: The height of each individual animation frame.
    *   `4`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.02`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `4`
*   **`loop`**: Indicates if the animation should loop.
    *   `1` (true)