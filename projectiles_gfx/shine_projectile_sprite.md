---
title: Shine Projectile Sprite
category: projectiles_gfx
---

---

# Shine Projectile Sprite

This document describes the sprite definition for the "shine" projectile in Noita, focusing on its visual representation and animation.

## Sprite Definition

The primary element is the `<Sprite>` tag, which defines the visual asset for the projectile.

### Key Attributes

*   **`filename`**: Specifies the path to the sprite image file.
    *   `data/projectiles_gfx/shine.png`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   `9.5`
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   `9.5`
*   **`default_animation`**: The name of the animation to be used by default.
    *   `fireball`

## Animation Definition

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes

*   **`name`**: The identifier for this animation.
    *   `fireball`
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `4`
*   **`frame_width`**: The width of each individual animation frame.
    *   `19`
*   **`frame_height`**: The height of each individual animation frame.
    *   `19`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.09`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `4`
*   **`loop`**: Determines if the animation should loop.
    *   `1` (meaning true/looping)