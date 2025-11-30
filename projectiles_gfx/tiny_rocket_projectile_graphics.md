---
title: Tiny Rocket Projectile Graphics
category: projectiles_gfx
---

---

# Tiny Rocket Projectile Graphics

This document describes the graphical assets for the "tiny rocket" projectile in Noita, as defined in `rocket_tiny.xml`.

## Sprite Definition

The primary sprite definition for the tiny rocket projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/rocket_tiny.png` - The texture file used for the projectile's appearance.
*   **offset_x**: `4.5` - Horizontal offset for the sprite's origin.
*   **offset_y**: `3` - Vertical offset for the sprite's origin.
*   **default_animation**: `fireball` - The name of the animation to be played by default.

## Animation: `fireball`

Defines the frame-by-frame animation for the projectile.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame_count**: `3` - The total number of frames in this animation.
*   **frame_width**: `12` - The width of each individual animation frame.
*   **frame_height**: `6` - The height of each individual animation frame.
*   **frame_wait**: `0.09` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `3` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).