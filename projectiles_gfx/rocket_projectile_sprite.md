---
title: Rocket Projectile Sprite
category: projectiles_gfx
---

# Rocket Projectile Sprite

This document details the sprite and animation data for the "rocket" projectile in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite definition for the rocket projectile.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/rocket.png` - Specifies the image file containing the rocket's visual assets.
*   **`default_animation`**: `fireball` - Sets the default animation to play when the projectile is active.
*   **`offset_x`**: `3` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `4.5` - Vertical offset for the sprite's origin.

## Animation: `fireball`

Defines the frame-by-frame animation for the rocket's visual effect.

### Key Attributes:

*   **`name`**: `fireball` - The identifier for this animation.
*   **`frame_count`**: `3` - The total number of frames in the animation.
*   **`frame_width`**: `13` - The width of each individual frame in pixels.
*   **`frame_height`**: `9` - The height of each individual frame in pixels.
*   **`frames_per_row`**: `3` - Indicates how many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.1` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`pos_x`**: `0` - The X-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **`pos_y`**: `1` - The Y-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - A flag indicating if frames should be shrunk by one pixel, potentially for visual effects or alignment.