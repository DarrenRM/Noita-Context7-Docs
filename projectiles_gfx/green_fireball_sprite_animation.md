---
title: Green Fireball Sprite Animation
category: projectiles_gfx
---

# Green Fireball Sprite Animation

This document describes the sprite animation for a smaller green fireball projectile in Noita.

## Sprite Definition

The primary sprite definition for the green fireball.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to use, which is "fireball".
*   **`filename`**: The path to the sprite sheet containing the animation frames.
    *   `data/projectiles_gfx/fireball_smaller_green.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `8`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `8`

## RectAnimation: "fireball"

Defines the rectangular animation sequence for the "fireball" animation.

### Key Attributes:

*   **`name`**: The name of this animation.
    *   `fireball`
*   **`frame_count`**: The total number of frames in the animation.
    *   `4`
*   **`frame_width`**: The width of each individual frame.
    *   `17`
*   **`frame_height`**: The height of each individual frame.
    *   `17`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `4`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.09`
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should be shrunk by one pixel.
    *   `1` (True)