---
title: Small Slimeball Projectile Graphics
category: projectiles_gfx
---

# Small Slimeball Projectile Graphics

This document details the graphical assets for the "slimeball_small" projectile in Noita, focusing on its sprite and animations.

## Sprite Definition

The primary sprite for the small slimeball is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/slimeball_small.png` - The path to the image file containing the projectile's graphics.
*   **offset_x**: `6` - Horizontal offset for the sprite's origin.
*   **offset_y**: `6` - Vertical offset for the sprite's origin.
*   **default_animation**: `spawn` - The animation to play by default when the projectile is created.

## Animations

The projectile utilizes two distinct animations: `spawn` and `fireball`.

### `spawn` Animation

This animation plays when the projectile is first created, likely a brief visual effect.

#### Key Attributes:

*   **name**: `spawn`
*   **pos_x**: `0` - Starting X position within the sprite sheet.
*   **pos_y**: `12` - Starting Y position within the sprite sheet.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `12` - The width of each individual frame.
*   **frame_height**: `12` - The height of each individual frame.
*   **frame_wait**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **next_animation**: `fireball` - The animation to transition to after this one completes.
*   **loop**: `0` - This animation does not loop.

### `fireball` Animation

This animation likely represents the projectile in its active, moving state.

#### Key Attributes:

*   **name**: `fireball`
*   **pos_x**: `0` - Starting X position within the sprite sheet.
*   **pos_y**: `0` - Starting Y position within the sprite sheet.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `12` - The width of each individual frame.
*   **frame_height**: `12` - The height of each individual frame.
*   **frame_wait**: `0.10` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - This animation loops indefinitely.