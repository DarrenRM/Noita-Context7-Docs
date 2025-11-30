---
title: Small Magic Fireball Sprite
category: projectiles_gfx
---

# Small Magic Fireball Sprite

This document details the sprite definition for the "small magic fireball" projectile in Noita, focusing on its visual representation and animation.

## Sprite Definition

The core sprite definition is provided by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: Specifies the texture file for the sprite.
    *   `data/projectiles_gfx/fireball_small_magic.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `2`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `2`
*   **`default_animation`**: The name of the animation to be played by default.
    *   `fireball`

## Animation Details

The visual animation of the fireball is defined within the `<RectAnimation>` tag.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `fireball`
*   **`pos_x`**: Starting X-coordinate of the animation frames within the texture.
    *   `0`
*   **`pos_y`**: Starting Y-coordinate of the animation frames within the texture.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `4`
*   **`frame_width`**: The width of each individual animation frame.
    *   `4`
*   **`frame_height`**: The height of each individual animation frame.
    *   `4`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.02`
*   **`frames_per_row`**: The number of frames arranged horizontally in the texture.
    *   `4`
*   **`loop`**: Indicates if the animation should loop.
    *   `1` (True)