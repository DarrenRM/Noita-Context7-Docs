---
title: Muzzle Launcher 03 Particle
category: particles
---

---

# Muzzle Launcher 03 Particle

This document describes the particle effect for `muzzle_launcher_03`, a muzzle flash effect used in Noita.

## Sprite

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_launcher_03.png` - The image file used for the sprite.
*   **offset_x**: `8` - Horizontal offset for the sprite.
*   **offset_y**: `7` - Vertical offset for the sprite.
*   **default_animation**: `muzzle` - The name of the default animation to play.

## RectAnimation

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The name of this animation, referenced by `default_animation` in the `Sprite` element.
*   **pos_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `16` - The width of each individual frame.
*   **frame_height**: `16` - The height of each individual frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).