---
title: Heavy Bullet Poison Sprite
category: projectiles_gfx
---

# Heavy Bullet Poison Sprite

This documentation describes the sprite definition for the "heavy_bullet_poison" projectile in Noita. It focuses on the visual representation and animation of this projectile.

## Sprite Definition

The core of the projectile's visual is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/heavy_bullet_poison.png`
    *   Specifies the texture file used for the sprite.
*   **offset_x**: `4`
    *   Horizontal offset of the sprite's origin.
*   **offset_y**: `4`
    *   Vertical offset of the sprite's origin.
*   **default_animation**: `fireball`
    *   The name of the animation to be played by default.

## Animation Definition

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `fireball`
    *   The identifier for this specific animation.
*   **pos_x**: `0`
    *   The starting X coordinate within the texture for the animation frames.
*   **pos_y**: `0`
    *   The starting Y coordinate within the texture for the animation frames.
*   **frame_count**: `1`
    *   The total number of frames in this animation.
*   **frame_width**: `8`
    *   The width of each individual animation frame.
*   **frame_height**: `8`
    *   The height of each individual animation frame.
*   **frame_wait**: `0.2`
    *   The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `4`
    *   Indicates how many frames are arranged horizontally in the texture file.
*   **loop**: `0`
    *   Specifies if the animation should loop (0 for no loop, 1 for loop).