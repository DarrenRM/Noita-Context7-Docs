---
title: Blast Projectile Graphics
category: projectiles_gfx
---

# Blast Projectile Graphics

This document details the graphical assets for the "blast" projectile in Noita, as defined in `blast.xml`. It focuses on the sprite and its associated animations.

## Sprite Definition

The main sprite for the blast projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/blast.png` - Specifies the image file containing the sprite frames.
*   **`default_animation`**: `"spawn"` - Sets the initial animation to play when the projectile is created.
*   **`offset_x`**: `"32"` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `"32"` - Vertical offset for the sprite's origin.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation sequence.

### `spawn` Animation

This animation is the default and plays upon projectile creation.

#### Key Attributes:

*   **`name`**: `"spawn"`
*   **`frame_count`**: `"5"` - Total number of frames in this animation.
*   **`frame_width`**: `"65"` - Width of each individual frame.
*   **`frame_height`**: `"65"` - Height of each individual frame.
*   **`frames_per_row`**: `"5"` - Number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `"0.02"` - Delay in seconds between frames.
*   **`loop`**: `"0"` - Indicates that this animation does not loop.
*   **`next_animation`**: `"fireball"` - The animation to transition to after `spawn` completes.
*   **`pos_x`**: `"0"` - X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **`pos_y`**: `"1"` - Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `"1"` - A flag that might affect how the sprite scales or renders.

### `fireball` Animation

This animation follows the `spawn` animation.

#### Key Attributes:

*   **`name`**: `"fireball"`
*   **`frame_count`**: `"5"` - Total number of frames in this animation.
*   **`frame_width`**: `"65"` - Width of each individual frame.
*   **`frame_height`**: `"65"` - Height of each individual frame.
*   **`frames_per_row`**: `"5"` - Number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `"0.01"` - Delay in seconds between frames.
*   **`pos_x`**: `"0"` - X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **`pos_y`**: `"66"` - Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `"1"` - A flag that might affect how the sprite scales or renders.