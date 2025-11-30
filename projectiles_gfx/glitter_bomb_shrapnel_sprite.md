---
title: Glitter Bomb Shrapnel Sprite
category: projectiles_gfx
---

# Glitter Bomb Shrapnel Sprite

This document describes the sprite definition for the shrapnel projectiles originating from the Glitter Bomb in Noita.

## Sprite Definition

The primary `Sprite` element defines the visual appearance and animation for the shrapnel.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/glitter_bomb_shrapnel.png` - Specifies the texture file used for the sprite.
*   **`default_animation`**: `fireball` - Sets the default animation to play when the sprite is active.
*   **`offset_x`**: `2.5` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `2.5` - Vertical offset for the sprite's origin.

## Animation Details

The `RectAnimation` element defines the specific frames and timing for the `fireball` animation.

### Key Attributes:

*   **`name`**: `fireball` - The name of this animation, referenced by `default_animation`.
*   **`frame_count`**: `3` - The total number of frames in the animation.
*   **`frame_width`**: `6` - The width of each individual frame in pixels.
*   **`frame_height`**: `6` - The height of each individual frame in pixels.
*   **`frames_per_row`**: `8` - The number of frames arranged horizontally in the texture file.
*   **`frame_wait`**: `0.12` - The duration in seconds each frame is displayed before transitioning to the next.
*   **`pos_x`**: `0` - The starting X-coordinate of the animation frames within the texture.
*   **`pos_y`**: `1` - The starting Y-coordinate of the animation frames within the texture.
*   **`shrink_by_one_pixel`**: `1` - Indicates that each frame should be shrunk by one pixel, likely for visual effect or to avoid pixel bleeding.