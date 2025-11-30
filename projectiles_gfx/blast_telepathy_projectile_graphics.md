---
title: Blast Telepathy Projectile Graphics
category: projectiles_gfx
---

# Blast Telepathy Projectile Graphics

This document details the graphical assets for the "Blast Telepathy" projectile in Noita, focusing on its sprite and animation definitions.

## Sprite Definition

The primary sprite for this projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/blast.png` - Specifies the texture file used for the sprite.
*   **`offset_x`**: `32` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `32` - Vertical offset for the sprite's origin.
*   **`color_r`, `color_g`, `color_b`, `color_a`**: `1`, `0.8`, `0.4`, `1` - Defines the base color tint of the sprite (Red, Green, Blue, Alpha).
*   **`default_animation`**: `spawn` - The animation that plays by default when the projectile is created.

## Animations

The projectile utilizes two distinct animations defined by `<RectAnimation>` tags: `spawn` and `fireball`.

### `spawn` Animation

This animation is typically used for the initial appearance or creation of the projectile.

#### Key Attributes:

*   **`name`**: `spawn` - The identifier for this animation.
*   **`frame_count`**: `5` - The total number of frames in this animation.
*   **`frame_width`**: `65` - The width of each individual frame.
*   **`frame_height`**: `65` - The height of each individual frame.
*   **`frames_per_row`**: `5` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0` - Indicates that this animation does not loop (plays once).
*   **`next_animation`**: `fireball` - The animation to transition to after this one completes.
*   **`pos_x`**: `0` - The starting X coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The starting Y coordinate of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - A flag indicating if frames should shrink by one pixel.

### `fireball` Animation

This animation likely represents the main visual state of the projectile while in motion.

#### Key Attributes:

*   **`name`**: `fireball` - The identifier for this animation.
*   **`frame_count`**: `5` - The total number of frames in this animation.
*   **`frame_width`**: `65` - The width of each individual frame.
*   **`frame_height`**: `65` - The height of each individual frame.
*   **`frames_per_row`**: `5` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.01` - The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**: `0` - The starting X coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: `66` - The starting Y coordinate of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - A flag indicating if frames should shrink by one pixel.