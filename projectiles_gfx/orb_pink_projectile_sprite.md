---
title: Orb Pink Projectile Sprite
category: projectiles_gfx
---

# Orb Pink Projectile Sprite

This document describes the sprite and animation data for the "orb_pink" projectile in Noita.

## Sprite Definition

The primary sprite for this projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/orb_pink.png` - Specifies the image file used for the sprite.
*   **offset_x**: `5` - Horizontal offset for the sprite's origin.
*   **offset_y**: `5` - Vertical offset for the sprite's origin.
*   **default_animation**: `fireball` - The name of the animation to be used by default.

## Animation Definition

The projectile utilizes a rectangular animation named "fireball".

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `4` - The total number of frames in the animation.
*   **frame_width**: `10` - The width of each individual frame.
*   **frame_height**: `10` - The height of each individual frame.
*   **frame_wait**: `0.07` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).