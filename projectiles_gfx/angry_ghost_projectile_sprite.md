---
title: Angry Ghost Projectile Sprite
category: projectiles_gfx
---

# Angry Ghost Projectile Sprite

This document details the sprite and animation data for the "angry_ghost" projectile in Noita.

## Sprite Definition

The main `<Sprite>` element defines the visual appearance and default animation for the projectile.

### Key Attributes:

*   **`default_animation`**: Specifies the animation to play by default.
    *   Value: `float_right`
*   **`filename`**: The path to the sprite sheet image.
    *   Value: `data/projectiles_gfx/angry_ghost.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `4.5`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `5`

## Animations

The `<Sprite>` element contains multiple `<RectAnimation>` elements, each defining a distinct animation sequence.

### `float_right` Animation

*   **`name`**: `float_right`
*   **`frame_count`**: `8`
*   **`frame_height`**: `10`
*   **`frame_wait`**: `0.14` (seconds per frame)
*   **`frame_width`**: `9`
*   **`frames_per_row`**: `12`
*   **`pos_x`**: `0`
*   **`pos_y`**: `0`

### `float_left` Animation

*   **`name`**: `float_left`
*   **`frame_count`**: `8`
*   **`frame_height`**: `10`
*   **`frame_wait`**: `0.14` (seconds per frame)
*   **`frame_width`**: `9`
*   **`frames_per_row`**: `8`
*   **`pos_x`**: `0`
*   **`pos_y`**: `10`

### `fly_right` Animation

*   **`name`**: `fly_right`
*   **`frame_count`**: `4`
*   **`frame_height`**: `10`
*   **`frame_wait`**: `0.08` (seconds per frame)
*   **`frame_width`**: `9`
*   **`frames_per_row`**: `8`
*   **`pos_x`**: `0`
*   **`pos_y`**: `20`

### `fly_left` Animation

*   **`name`**: `fly_left`
*   **`frame_count`**: `4`
*   **`frame_height`**: `10`
*   **`frame_wait`**: `0.08` (seconds per frame)
*   **`frame_width`**: `9`
*   **`frames_per_row`**: `8`
*   **`pos_x`**: `0`
*   **`pos_y`**: `30`