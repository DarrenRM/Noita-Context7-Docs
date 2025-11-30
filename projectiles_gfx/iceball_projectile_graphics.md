---
title: Iceball Projectile Graphics
category: projectiles_gfx
---

# Iceball Projectile Graphics

This document details the graphical assets for the "iceball" projectile in Noita, as defined in `iceball.xml`.

## Sprite Definition

The primary sprite definition for the iceball projectile.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/iceball.png` - Specifies the image file containing the projectile's graphics.
*   **`default_animation`**: `"spawn"` - Sets the initial animation to play when the projectile is created.
*   **`offset_x`**: `"16"` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `"12"` - Vertical offset for the sprite's origin.

## Animations

The `Sprite` element contains definitions for different animations used by the projectile.

### `fireball` Animation

This animation likely represents the active state of the iceball.

#### Key Attributes:

*   **`name`**: `"fireball"`
*   **`frame_count`**: `"4"` - Total number of frames in this animation.
*   **`frame_width`**: `"33"` - Width of each frame.
*   **`frame_height`**: `"25"` - Height of each frame.
*   **`frame_wait`**: `"0.035"` - Time in seconds to wait between frames.
*   **`frames_per_row`**: `"4"` - Number of frames arranged horizontally in the sprite sheet.
*   **`pos_x`**: `"0"` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **`pos_y`**: `"1"` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **`shrink_by_one_pixel`**: `"1"` - Indicates if each frame should be shrunk by one pixel.

### `spawn` Animation

This animation likely represents the initial appearance or spawning effect of the iceball.

#### Key Attributes:

*   **`name`**: `"spawn"`
*   **`frame_count`**: `"4"` - Total number of frames in this animation.
*   **`frame_width`**: `"32"` - Width of each frame.
*   **`frame_height`**: `"24"` - Height of each frame.
*   **`frame_wait`**: `"0.08"` - Time in seconds to wait between frames.
*   **`frames_per_row`**: `"4"` - Number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `"0"` - This animation does not loop.
*   **`next_animation`**: `"fireball"` - After this animation finishes, it transitions to the `fireball` animation.
*   **`pos_x`**: `"0"` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **`pos_y`**: `"26"` - Y-coordinate of the animation's top-left corner within the sprite sheet.