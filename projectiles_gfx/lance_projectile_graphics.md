---
title: Lance Projectile Graphics
category: projectiles_gfx
---

# Lance Projectile Graphics

This document details the graphical assets for the "lance" projectile in Noita, as defined in `lance.xml`.

## Sprite Definition

The primary sprite for the lance projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/lance.png` - The path to the image file containing the projectile's graphics.
*   **offset_x**: `8` - Horizontal offset for the sprite.
*   **offset_y**: `2.5` - Vertical offset for the sprite.
*   **default_animation**: `"fireball"` - Specifies the default animation to be used for this sprite.

## Animation Definition

The projectile utilizes a single animation named "fireball".

### Key Attributes:

*   **name**: `"fireball"` - The identifier for this animation.
*   **pos_x**: `"0"` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `"0"` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `"1"` - The total number of frames in this animation.
*   **frame_width**: `"16"` - The width of each individual frame.
*   **frame_height**: `"5"` - The height of each individual frame.
*   **frame_wait**: `"0.2"` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `"1"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates whether the animation should loop (1 for true, 0 for false).