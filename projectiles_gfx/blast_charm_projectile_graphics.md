---
title: Blast Charm Projectile Graphics
category: projectiles_gfx
---

# Blast Charm Projectile Graphics

This document details the graphical assets for the "Blast Charm" projectile in Noita, focusing on its sprite and animation definitions.

## Sprite Definition

The main sprite for the blast charm projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/blast.png` - Specifies the texture file used for the sprite.
*   **`offset_x`**: `32` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `32` - Vertical offset for the sprite's origin.
*   **`color_r`, `color_g`, `color_b`, `color_a`**: `1`, `0.95`, `0.7`, `1` - Defines the base color tint of the sprite (Red, Green, Blue, Alpha).
*   **`default_animation`**: `spawn` - The animation to play by default when the projectile is created.

## Animation Definitions

The projectile utilizes multiple `RectAnimation` blocks to define different animation sequences.

### `spawn` Animation

This animation is the initial visual effect when the projectile appears.

#### Key Attributes:

*   **`name`**: `spawn` - Identifier for this animation.
*   **`frame_count`**: `5` - Total number of frames in this animation.
*   **`frame_width`**: `65` - Width of each individual frame.
*   **`frame_height`**: `65` - Height of each individual frame.
*   **`frames_per_row`**: `5` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0` - Indicates that this animation does not loop (plays once).
*   **`next_animation`**: `fireball` - The animation to transition to after this one completes.
*   **`pos_x`**: `0` - The starting X coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The starting Y coordinate of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - A visual effect that shrinks the sprite by one pixel per frame.

### `fireball` Animation

This animation represents the projectile in its active, moving state.

#### Key Attributes:

*   **`name`**: `fireball` - Identifier for this animation.
*   **`frame_count`**: `5` - Total number of frames in this animation.
*   **`frame_width`**: `65` - Width of each individual frame.
*   **`frame_height`**: `65` - Height of each individual frame.
*   **`frames_per_row`**: `5` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.01` - The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**: `0` - The starting X coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: `66` - The starting Y coordinate of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - A visual effect that shrinks the sprite by one pixel per frame.