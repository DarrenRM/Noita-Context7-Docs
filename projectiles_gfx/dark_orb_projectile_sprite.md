---
title: Dark Orb Projectile Sprite
category: projectiles_gfx
---

# Dark Orb Projectile Sprite

This document describes the sprite and animation data for the "Dark Orb" projectile in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite definition for the Dark Orb projectile.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to use.
    *   Value: `"fireball"`
*   **`filename`**: The path to the sprite sheet image file.
    *   Value: `"data/projectiles_gfx/orb_dark.png"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"5"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"5"`

## Animation: `fireball`

Defines the "fireball" animation sequence for the Dark Orb.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   Value: `"fireball"`
*   **`frame_count`**: The total number of frames in the animation.
    *   Value: `"4"`
*   **`frame_width`**: The width of each individual frame.
    *   Value: `"11"`
*   **`frame_height`**: The height of each individual frame.
    *   Value: `"11"`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   Value: `"4"`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   Value: `"0.07"`
*   **`pos_x`**: The starting X-coordinate of the animation frames within the sprite sheet.
    *   Value: `"0"`
*   **`pos_y`**: The starting Y-coordinate of the animation frames within the sprite sheet.
    *   Value: `"1"`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should be shrunk by one pixel.
    *   Value: `"1"`