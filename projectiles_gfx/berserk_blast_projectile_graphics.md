---
title: Berserk Blast Projectile Graphics
category: projectiles_gfx
---

# Berserk Blast Projectile Graphics

This document details the graphical assets for the "Berserk Blast" projectile in Noita, as defined in `blast_berserk.xml`.

## Sprite Definition

The primary visual representation of the projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/blast.png` - Specifies the texture file used for the sprite.
*   **`offset_x`**, **`offset_y`**: `32`, `32` - Defines the center point of the sprite relative to its origin.
*   **`color_r`**, **`color_g`**, **`color_b`**, **`color_a`**: `1`, `0.5`, `0.5`, `1` - Sets the red, green, blue, and alpha color channels for tinting the sprite. This results in a reddish-orange tint.
*   **`default_animation`**: `spawn` - Indicates the animation to play by default when the projectile is created.

## Animations

The projectile utilizes multiple `RectAnimation` blocks to define different animation sequences.

### `spawn` Animation

This animation plays when the projectile is first created.

*   **`name`**: `spawn`
*   **`frame_count`**: `5` - Total number of frames in this animation.
*   **`frame_width`**, **`frame_height`**: `65`, `65` - Dimensions of each individual frame.
*   **`frames_per_row`**: `5` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0` - This animation does not loop.
*   **`next_animation`**: `fireball` - After completing, it transitions to the `fireball` animation.
*   **`pos_x`**, **`pos_y`**: `0`, `1` - The starting X and Y coordinates (in pixels) on the sprite sheet for this animation's frames.
*   **`shrink_by_one_pixel`**: `1` - Indicates that frames should shrink by one pixel each iteration.

### `fireball` Animation

This animation plays after the `spawn` animation completes, representing the projectile in its active state.

*   **`name`**: `fireball`
*   **`frame_count`**: `5` - Total number of frames in this animation.
*   **`frame_width`**, **`frame_height`**: `65`, `65` - Dimensions of each individual frame.
*   **`frames_per_row`**: `5` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.01` - The duration (in seconds) each frame is displayed before advancing. This is faster than the `spawn` animation.
*   **`pos_x`**, **`pos_y`**: `0`, `66` - The starting X and Y coordinates (in pixels) on the sprite sheet for this animation's frames. Note the `pos_y` is offset from the `spawn` animation.
*   **`shrink_by_one_pixel`**: `1` - Indicates that frames should shrink by one pixel each iteration.