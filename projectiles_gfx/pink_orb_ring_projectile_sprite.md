---
title: Pink Orb Ring Projectile Sprite
category: projectiles_gfx
---

# Pink Orb Ring Projectile Sprite

This document describes the sprite data for the "orb_pink_ring" projectile in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite for this projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/orb_pink_ring.png` - Specifies the image file used for the sprite.
*   **`default_animation`**: `fireball` - Sets the default animation to be played.
*   **`offset_x`**: `8` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `8` - Vertical offset for the sprite's origin.

## Animation: `fireball`

The `fireball` animation is a rectangular animation, meaning it uses a grid of frames within the sprite sheet.

### Key Attributes:

*   **`name`**: `fireball` - The name of this animation.
*   **`frame_count`**: `4` - The total number of frames in this animation.
*   **`frame_width`**: `17` - The width of each individual frame.
*   **`frame_height`**: `17` - The height of each individual frame.
*   **`frame_wait`**: `0.06` - The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **`pos_x`**: `0` - The starting X-coordinate of the animation grid within the sprite sheet.
*   **`pos_y`**: `1` - The starting Y-coordinate of the animation grid within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - Indicates that each frame should be shrunk by one pixel.