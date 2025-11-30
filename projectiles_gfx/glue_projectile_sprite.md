---
title: Glue Projectile Sprite
category: projectiles_gfx
---

# Glue Projectile Sprite

This documentation describes the sprite definition for the "glue" projectile in Noita. It focuses on the visual representation and animation of this projectile.

## Sprite Definition

The main `<Sprite>` element defines the base image and its properties.

### Key Attributes:

*   **`filename`**: Specifies the path to the sprite image file.
    *   `data/projectiles_gfx/glue.png`
*   **`offset_x`**: Horizontal offset for the sprite's position.
    *   `9`
*   **`offset_y`**: Vertical offset for the sprite's position.
    *   `4`
*   **`default_animation`**: The name of the animation to use by default.
    *   `fireball`

## Animation Definition

The `<RectAnimation>` element defines how the sprite is animated.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `fireball`
*   **`pos_x`**: Starting X position within the sprite sheet for the animation.
    *   `0`
*   **`pos_y`**: Starting Y position within the sprite sheet for the animation.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `1`
*   **`frame_width`**: The width of each individual frame.
    *   `18`
*   **`frame_height`**: The height of each individual frame.
    *   `8`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed.
    *   `0.09`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `1`
*   **`loop`**: Whether the animation should loop.
    *   `1` (true)