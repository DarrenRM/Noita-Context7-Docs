---
title: Death Ghost Projectile Sprite
category: projectiles_gfx
---

# Death Ghost Projectile Sprite

This document details the sprite information for the "death_ghost" projectile in Noita, used for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the visual properties and default animation for the projectile.

### Key Attributes:

*   **`default_animation`**: Specifies the animation to play by default.
    *   Value: `float_right`
*   **`filename`**: The path to the sprite image file.
    *   Value: `data/projectiles_gfx/death_ghost.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `4.5`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `5`

## Animation Definitions

The `<RectAnimation>` tags define different animation sequences for the sprite. Each animation is composed of frames from the specified `filename`.

### `float_right` Animation

This animation likely represents the ghost floating to the right.

*   **`name`**: `float_right`
*   **`frame_count`**: `8` (Total number of frames in this animation)
*   **`frame_height`**: `10` (Height of each individual frame)
*   **`frame_wait`**: `0.14` (Time in seconds each frame is displayed)
*   **`frame_width`**: `9` (Width of each individual frame)
*   **`frames_per_row`**: `12` (Number of frames that fit horizontally in the sprite sheet row)
*   **`pos_x`**: `0` (X-coordinate of the top-left corner of the animation frames in the sprite sheet)
*   **`pos_y`**: `0` (Y-coordinate of the top-left corner of the animation frames in the sprite sheet)

### `float_left` Animation

This animation likely represents the ghost floating to the left.

*   **`name`**: `float_left`
*   **`frame_count`**: `8`
*   **`frame_height`**: `10`
*   **`frame_wait`**: `0.14`
*   **`frame_width`**: `9`
*   **`frames_per_row`**: `8`
*   **`pos_x`**: `0`
*   **`pos_y`**: `10`

### `fly_right` Animation

This animation likely represents the ghost flying to the right.

*   **`name`**: `fly_right`
*   **`frame_count`**: `4`
*   **`frame_height`**: `10`
*   **`frame_wait`**: `0.08`
*   **`frame_width`**: `9`
*   **`frames_per_row`**: `8`
*   **`pos_x`**: `0`
*   **`pos_y`**: `20`

### `fly_left` Animation

This animation likely represents the ghost flying to the left.

*   **`name`**: `fly_left`
*   **`frame_count`**: `4`
*   **`frame_height`**: `10`
*   **`frame_wait`**: `0.08`
*   **`frame_width`**: `9`
*   **`frames_per_row`**: `8`
*   **`pos_x`**: `0`
*   **`pos_y`**: `30`