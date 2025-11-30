---
title: Purple Grenade Sprite
category: projectiles_gfx
---

# Purple Grenade Sprite

This document describes the sprite definition for the "purple grenade" projectile in Noita. It focuses on the visual aspects and animation of the projectile.

## Sprite Definition

The main `<Sprite>` element defines the base image and its properties.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the sprite.
    *   `data/projectiles_gfx/grenade_purple.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `4`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `4`
*   **`default_animation`**: The name of the animation to play by default.
    *   `fireball`

## Animation: `fireball`

The `<RectAnimation>` element defines the animation sequence for the sprite.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `fireball`
*   **`pos_x`**: Starting X position within the sprite sheet for the animation frames.
    *   `0`
*   **`pos_y`**: Starting Y position within the sprite sheet for the animation frames.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `4`
*   **`frame_width`**: The width of each individual animation frame.
    *   `8`
*   **`frame_height`**: The height of each individual animation frame.
    *   `8`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.04`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `4`
*   **`loop`**: Indicates if the animation should loop.
    *   `1` (True - the animation will repeat)