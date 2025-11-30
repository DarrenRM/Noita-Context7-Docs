---
title: Skull Projectile Sprite
category: projectiles_gfx
---

# Skull Projectile Sprite

This documentation describes the sprite and animation data for the "skull" projectile in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual appearance and initial positioning of the projectile.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the sprite.
    *   `data/projectiles_gfx/skull.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `6`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `6.5`
*   **`default_animation`**: The name of the animation to play by default.
    *   `fireball`

## Animation Definition

The `<RectAnimation>` element defines the frame-by-frame animation for the sprite.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `fireball`
*   **`pos_x`**: X-coordinate of the top-left corner of the animation frames within the texture.
    *   `0`
*   **`pos_y`**: Y-coordinate of the top-left corner of the animation frames within the texture.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `3`
*   **`frame_width`**: The width of each individual animation frame.
    *   `12`
*   **`frame_height`**: The height of each individual animation frame.
    *   `13`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.09`
*   **`frames_per_row`**: The number of frames arranged horizontally in the texture.
    *   `4`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`