---
title: Darkball Projectile Sprite
category: projectiles_gfx
---

# Darkball Projectile Sprite

This documentation describes the sprite and animation data for the "darkball" projectile in Noita.

## Sprite Definition

The primary sprite for the darkball is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/darkball.png` - Specifies the image file used for the sprite.
*   **`offset_x`**: `32` - The horizontal offset of the sprite's origin.
*   **`offset_y`**: `32` - The vertical offset of the sprite's origin.
*   **`default_animation`**: `fireball` - The name of the animation to be used by default.

## Animation Definition

The animation for the darkball is defined by the `<RectAnimation>` tag.

### Key Attributes:

*   **`name`**: `fireball` - The identifier for this animation.
*   **`pos_x`**: `0` - The starting X position within the sprite sheet for the animation frames.
*   **`pos_y`**: `0` - The starting Y position within the sprite sheet for the animation frames.
*   **`frame_count`**: `1` - The total number of frames in this animation.
*   **`frame_width`**: `64` - The width of each individual animation frame.
*   **`frame_height`**: `64` - The height of each individual animation frame.
*   **`frame_wait`**: `0.2` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `1` - Indicates that the animation should loop (1 for true, 0 for false).