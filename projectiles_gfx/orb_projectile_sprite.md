---
title: Orb Projectile Sprite
category: projectiles_gfx
---

---

# Orb Projectile Sprite

This documentation describes the sprite definition for the "orb" projectile in Noita. It focuses on the visual representation and animation of this projectile.

## Sprite Definition

The main `<Sprite>` element defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/orb.png` - The path to the image file containing the orb's sprite.
*   **offset_x**: `5` - Horizontal offset for the sprite's origin.
*   **offset_y**: `5` - Vertical offset for the sprite's origin.
*   **default_animation**: `fireball` - The name of the animation that plays by default.

## Animation Definition

The `<RectAnimation>` element defines the animation sequence for the orb.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - The starting X coordinate of the animation frames within the sprite sheet.
*   **pos_y**: `0` - The starting Y coordinate of the animation frames within the sprite sheet.
*   **frame_count**: `4` - The total number of frames in the animation.
*   **frame_width**: `10` - The width of each individual animation frame.
*   **frame_height**: `10` - The height of each individual animation frame.
*   **frame_wait**: `0.09` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `4` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).