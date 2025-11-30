---
title: Heal Ghost Projectile Sprite
category: projectiles_gfx
---

# Heal Ghost Projectile Sprite

This document details the sprite definition for the "heal_ghost" projectile in Noita, focusing on its visual representation and animation.

## Sprite Definition

The core of the projectile's visual is defined by the `<Sprite>` tag.

### Key Attributes

*   **`filename`**: `data/projectiles_gfx/heal_ghost.png` - Specifies the image file containing the sprite's frames.
*   **`default_animation`**: `float_right` - Sets the animation to play by default when the projectile is spawned.
*   **`offset_x`**: `4.5` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `5` - Vertical offset for the sprite's origin.

## Animations

The projectile utilizes multiple `RectAnimation` tags to define different movement and visual states. Each animation is a sequence of frames extracted from the `heal_ghost.png` file.

### `float_right` Animation

*   **`name`**: `float_right`
*   **`frame_count`**: `8` - Total number of frames in this animation.
*   **`frame_height`**: `10` - Height of each individual frame.
*   **`frame_wait`**: `0.14` - Time in seconds to wait between frames.
*   **`frame_width`**: `9` - Width of each individual frame.
*   **`frames_per_row`**: `12` - Number of frames arranged horizontally in the sprite sheet.
*   **`pos_x`**: `0` - X-coordinate of the top-left corner of this animation's frames within the sprite sheet.
*   **`pos_y`**: `0` - Y-coordinate of the top-left corner of this animation's frames within the sprite sheet.

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