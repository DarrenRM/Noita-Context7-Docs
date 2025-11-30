---
title: Shield Ghost Projectile Graphics
category: projectiles_gfx
---

# Shield Ghost Projectile Graphics

This document details the graphical assets for the "Shield Ghost" projectile in Noita, focusing on its sprite and animation definitions.

## Sprite Definition

The main sprite for the Shield Ghost projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`default_animation`**: Specifies the animation to play by default.
    *   Value: `float_right`
*   **`filename`**: The path to the image file containing the sprite frames.
    *   Value: `data/projectiles_gfx/shield_ghost.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `4.5`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `5`

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation sequence.

### `float_right` Animation

*   **`name`**: `float_right`
*   **`frame_count`**: `8` (Number of frames in this animation)
*   **`frame_height`**: `10` (Height of each frame)
*   **`frame_wait`**: `0.14` (Time in seconds each frame is displayed)
*   **`frame_width`**: `9` (Width of each frame)
*   **`frames_per_row`**: `12` (Number of frames in a single row of the sprite sheet)
*   **`pos_x`**: `0` (X-coordinate of the top-left corner of this animation's frames on the sprite sheet)
*   **`pos_y`**: `0` (Y-coordinate of the top-left corner of this animation's frames on the sprite sheet)

### `float_left` Animation

*   **`name`**: `float_left`
*   **`frame_count`**: `8`
*   **`frame_height`**: `10`
*   **`frame_wait`**: `0.14`
*   **`frame_width`**: `9`
*   **`frames_per_row`**: `8`
*   **`pos_x`**: `0`
*   **`pos_y`**: `10`

### `fly_right` Animation

*   **`name`**: `fly_right`
*   **`frame_count`**: `4`
*   **`frame_height`**: `10`
*   **`frame_wait`**: `0.08`
*   **`frame_width`**: `9`
*   **`frames_per_row`**: `8`
*   **`pos_x`**: `0`
*   **`pos_y`**: `20`

### `fly_left` Animation

*   **`name`**: `fly_left`
*   **`frame_count`**: `4`
*   **`frame_height`**: `10`
*   **`frame_wait`**: `0.08`
*   **`frame_width`**: `9`
*   **`frames_per_row`**: `8`
*   **`pos_x`**: `0`
*   **`pos_y`**: `30`