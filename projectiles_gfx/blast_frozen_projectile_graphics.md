---
title: Blast Frozen Projectile Graphics
category: projectiles_gfx
---

# Blast Frozen Projectile Graphics

This document details the graphical assets for the "blast_frozen" projectile in Noita, focusing on its sprite and animation definitions.

## Sprite Definition

The primary sprite for the "blast_frozen" projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/projectiles_gfx/blast.png` - Specifies the image file containing the sprite frames.
*   **`offset_x`**: `32` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `32` - Vertical offset for the sprite's origin.
*   **`color_r`, `color_g`, `color_b`, `color_a`**: These attributes define the base color tint of the sprite. In this case, it's a slightly desaturated reddish-white.

## Animation Definitions

The projectile utilizes multiple animations defined by `<RectAnimation>` tags within the `<Sprite>` definition.

### Animation: `spawn`

This animation likely represents the initial appearance or spawning effect of the projectile.

#### Key Attributes:

*   **`name`**: `spawn` - The identifier for this animation.
*   **`frame_count`**: `5` - The total number of frames in this animation.
*   **`frame_width`**: `65` - The width of each individual frame.
*   **`frame_height`**: `65` - The height of each individual frame.
*   **`frames_per_row`**: `5` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0` - Indicates that this animation does not loop.
*   **`next_animation`**: `fireball` - Specifies the animation to transition to after `spawn` completes.
*   **`pos_x`**: `0` - The horizontal starting position of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The vertical starting position of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - Suggests a visual effect where frames might shrink slightly.

### Animation: `fireball`

This animation likely represents the main visual of the projectile in motion.

#### Key Attributes:

*   **`name`**: `fireball` - The identifier for this animation.
*   **`frame_count`**: `5` - The total number of frames in this animation.
*   **`frame_width`**: `65` - The width of each individual frame.
*   **`frame_height`**: `65` - The height of each individual frame.
*   **`frames_per_row`**: `5` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.01` - The duration (in seconds) each frame is displayed before advancing. This is faster than the `spawn` animation.
*   **`pos_x`**: `0` - The horizontal starting position of the animation frames within the sprite sheet.
*   **`pos_y`**: `66` - The vertical starting position of the animation frames within the sprite sheet, indicating these frames are located below the `spawn` frames.
*   **`shrink_by_one_pixel`**: `1` - Suggests a visual effect where frames might shrink slightly.