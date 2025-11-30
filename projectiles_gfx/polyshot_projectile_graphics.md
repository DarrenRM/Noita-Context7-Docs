---
title: Polyshot Projectile Graphics
category: projectiles_gfx
---

# Polyshot Projectile Graphics

This document details the graphical assets for the "polyshot" projectile in Noita, as defined in `polyshot.xml`. It focuses on the sprite definition and its associated animations.

## Sprite Definition

The main sprite for the polyshot projectile is defined by the `<Sprite>` tag.

### Key Attributes

*   **filename**: `data/projectiles_gfx/polyshot.png` - Specifies the texture file containing the projectile's graphics.
*   **offset_x**: `12` - The horizontal offset of the sprite's origin.
*   **offset_y**: `12` - The vertical offset of the sprite's origin.
*   **default_animation**: `"spawn"` - The animation that plays by default when the projectile is created.

## Animations

The projectile utilizes two distinct animations: `spawn` and `fireball`.

### `spawn` Animation

This animation plays when the projectile is initially created, likely a brief visual effect.

#### Key Attributes

*   **name**: `"spawn"`
*   **pos_x**: `0` - The starting X coordinate within the sprite sheet for this animation.
*   **pos_y**: `24` - The starting Y coordinate within the sprite sheet for this animation.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `24` - The width of each individual frame.
*   **frame_height**: `24` - The height of each individual frame.
*   **frame_wait**: `0.02` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **next_animation**: `"fireball"` - The animation to transition to after this one completes.
*   **loop**: `0` - Indicates that this animation does not loop (it plays once).

### `fireball` Animation

This animation represents the main visual of the projectile in flight.

#### Key Attributes

*   **name**: `"fireball"`
*   **pos_x**: `0` - The starting X coordinate within the sprite sheet for this animation.
*   **pos_y**: `0` - The starting Y coordinate within the sprite sheet for this animation.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `24` - The width of each individual frame.
*   **frame_height**: `24` - The height of each individual frame.
*   **frame_wait**: `0.10` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that this animation loops indefinitely.