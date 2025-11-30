---
title: Darkball Center Projectile Sprite
category: projectiles_gfx
---

# Darkball Center Projectile Sprite

This document describes the sprite definition for the "darkball_center" projectile in Noita, focusing on its visual representation and animation.

## Sprite Definition

The core sprite for the darkball projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/darkball_center.png` - Specifies the image file used for the sprite.
*   **offset_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset_y**: `8` - The vertical offset of the sprite's origin.
*   **default_animation**: `fireball` - The name of the animation to be used by default.

## Animation Definition

The projectile utilizes a rectangular animation for its visual effect.

### Key Attributes of `RectAnimation`:

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - The starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - The starting Y position within the sprite sheet for the animation.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `16` - The width of each individual frame.
*   **frame_height**: `16` - The height of each individual frame.
*   **frame_wait**: `0.2` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).