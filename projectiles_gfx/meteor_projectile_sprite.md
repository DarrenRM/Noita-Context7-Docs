---
title: Meteor Projectile Sprite
category: projectiles_gfx
---

# Meteor Projectile Sprite

This documentation describes the sprite and animation data for the "meteor" projectile in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual appearance and animation of the projectile.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the sprite.
    *   `data/projectiles_gfx/meteor.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `12`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `12`
*   **`default_animation`**: The name of the animation to play by default.
    *   `default`

## Animation Definition

The `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `default`
*   **`pos_x`**: Starting X position within the sprite sheet for the animation frames.
    *   `0`
*   **`pos_y`**: Starting Y position within the sprite sheet for the animation frames.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `4`
*   **`frame_width`**: The width of each individual animation frame.
    *   `24`
*   **`frame_height`**: The height of each individual animation frame.
    *   `24`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.09`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `4`
*   **`loop`**: Determines if the animation should loop.
    *   `1` (loops)