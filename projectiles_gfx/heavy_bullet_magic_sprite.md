---
title: Heavy Bullet Magic Sprite
category: projectiles_gfx
---

---

# Heavy Bullet Magic Sprite

This documentation describes the sprite definition for the "heavy_bullet_magic" projectile in Noita. It focuses on the visual representation and animation of this projectile.

## Sprite Definition

The main `<Sprite>` element defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/heavy_bullet_magic.png` - The path to the sprite image file.
*   **offset_x**: `4` - Horizontal offset for the sprite's origin.
*   **offset_y**: `4` - Vertical offset for the sprite's origin.
*   **default_animation**: `"fireball"` - Specifies the default animation to be used.

## Animation Definition

The `<RectAnimation>` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `"fireball"` - The name of this animation, referenced by `default_animation`.
*   **pos_x**: `"0"` - The starting X-coordinate of the animation frames within the sprite sheet.
*   **pos_y**: `"0"` - The starting Y-coordinate of the animation frames within the sprite sheet.
*   **frame_count**: `"1"` - The total number of frames in the animation.
*   **frame_width**: `"8"` - The width of each individual frame.
*   **frame_height**: `"8"` - The height of each individual frame.
*   **frame_wait**: `"0.2"` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `"4"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"0"` - Indicates whether the animation should loop (0 for no loop, 1 for loop).