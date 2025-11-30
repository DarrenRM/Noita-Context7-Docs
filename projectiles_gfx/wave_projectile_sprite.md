---
title: Wave Projectile Sprite
category: projectiles_gfx
---

---

# Wave Projectile Sprite

This document describes the sprite definition for the "wave" projectile in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual appearance and animation of the projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/wave.png` - The path to the sprite image file.
*   **offset_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset_y**: `4` - Vertical offset for the sprite's origin.
*   **default_animation**: `fireball` - The name of the default animation to play.

## Animation Definition

The `<RectAnimation>` tag specifies the animation details.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `16` - The width of each individual frame.
*   **frame_height**: `8` - The height of each individual frame.
*   **frame_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).