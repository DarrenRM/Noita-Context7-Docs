---
title: Bullet Magic Sprite
category: projectiles_gfx
---

# Bullet Magic Sprite

This document describes the sprite definition for the "bullet_magic" projectile in Noita. It details the visual appearance and animation of this projectile.

## Sprite Definition

The main `<Sprite>` element defines the base visual properties and the default animation.

### Key Attributes

*   **`default_animation`**: Specifies the name of the animation to be used by default.
    *   Value: `"fireball"`
*   **`filename`**: The path to the image file containing the sprite's frames.
    *   Value: `"data/projectiles_gfx/bullet_magic.png"`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   Value: `"0.5"` (50% of the sprite's width)
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   Value: `"0.5"` (50% of the sprite's height)

## Animation: `fireball`

The `<RectAnimation>` element defines the specific animation sequence for the "fireball" state.

### Key Attributes

*   **`name`**: The identifier for this animation.
    *   Value: `"fireball"`
*   **`frame_count`**: The total number of frames in the animation.
    *   Value: `"4"`
*   **`frame_width`**: The width of each individual frame in pixels.
    *   Value: `"5"`
*   **`frame_height`**: The height of each individual frame in pixels.
    *   Value: `"2"`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   Value: `"4"`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   Value: `"0.2"`
*   **`loop`**: Determines if the animation should loop.
    *   Value: `"0"` (False - plays once)
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet (in grid units).
    *   Value: `"0"`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet (in grid units).
    *   Value: `"1"`
*   **`shrink_by_one_pixel`**: Indicates if frames should shrink by one pixel each step.
    *   Value: `"1"` (True)