---
title: Kallo Projectile Sprite
category: projectiles_gfx
---

# Kallo Projectile Sprite

This document describes the sprite and animation data for the "kallo" projectile in Noita.

## Sprite Definition

The primary sprite for the "kallo" projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/kallo.png` - Specifies the image file used for the sprite.
*   **offset_x**: `7` - Horizontal offset of the sprite's origin.
*   **offset_y**: `8` - Vertical offset of the sprite's origin.
*   **default_animation**: `fireball` - The name of the animation to be used by default.

## Animation Definition

The projectile utilizes a single animation named "fireball".

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `16` - The width of each individual animation frame.
*   **frame_height**: `16` - The height of each individual animation frame.
*   **frame_wait**: `0.2` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).