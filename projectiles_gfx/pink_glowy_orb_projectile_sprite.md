---
title: Pink Glowy Orb Projectile Sprite
category: projectiles_gfx
---

# Pink Glowy Orb Projectile Sprite

This document describes the sprite data for the "orb_pink_glowy" projectile in Noita.

## Sprite Definition

The primary sprite definition for this projectile is handled by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/orb_pink_glowy.png` - Specifies the image file used for the sprite.
*   **`default_animation`**: `fireball` - Sets the default animation to be played.
*   **`offset_x`**: `8` - Horizontal offset for the sprite.
*   **`offset_y`**: `8` - Vertical offset for the sprite.

## Animation: `fireball`

The `<RectAnimation>` tag defines the animation sequence for the "fireball" state.

### Key Attributes:

*   **`name`**: `fireball` - The name of this specific animation.
*   **`frame_count`**: `4` - The total number of frames in the animation.
*   **`frame_width`**: `17` - The width of each individual frame.
*   **`frame_height`**: `17` - The height of each individual frame.
*   **`frames_per_row`**: `7` - The number of frames arranged horizontally in the source image.
*   **`frame_wait`**: `0.06` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`pos_x`**: `0` - The X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - Indicates that each frame should be shrunk by one pixel.