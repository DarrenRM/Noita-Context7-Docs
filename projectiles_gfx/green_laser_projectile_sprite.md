---
title: Green Laser Projectile Sprite
category: projectiles_gfx
---

# Green Laser Projectile Sprite

This document describes the sprite definition for the "green laser" projectile in Noita. It focuses on the visual aspects and animation of this projectile.

## Sprite Definition

The primary sprite for the green laser is defined by the `<Sprite>` tag.

### Key Attributes

*   **filename**: `data/projectiles_gfx/laser_green.png` - Specifies the image file used for the sprite.
*   **offset_x**: `3` - Horizontal offset of the sprite from its origin.
*   **offset_y**: `1` - Vertical offset of the sprite from its origin.
*   **default_animation**: `fireball` - The name of the animation that plays by default.

## Animation Definition

The projectile uses a `RectAnimation` to define its visual sequence.

### Key Attributes

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `2` - The total number of frames in this animation.
*   **frame_width**: `8` - The width of each individual frame.
*   **frame_height**: `3` - The height of each individual frame.
*   **frame_wait**: `0.02` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `2` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).