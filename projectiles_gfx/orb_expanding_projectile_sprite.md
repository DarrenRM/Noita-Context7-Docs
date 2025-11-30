---
title: Orb Expanding Projectile Sprite
category: projectiles_gfx
---

# Orb Expanding Projectile Sprite

This document describes the sprite and animation data for the "orb_expanding" projectile in Noita.

## Sprite Definition

The primary sprite for this projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/orb_expanding.png` - The texture file used for the sprite.
*   **offset_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset_y**: `8` - Vertical offset for the sprite's origin.
*   **default_animation**: `fireball` - The name of the animation to play by default.

## Animation Definition

The projectile utilizes a `RectAnimation` for its visual sequence.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `12` - The total number of frames in the animation.
*   **frame_width**: `16` - The width of each individual frame.
*   **frame_height**: `16` - The height of each individual frame.
*   **frame_wait**: `0.16` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `12` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).