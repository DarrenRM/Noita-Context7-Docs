---
title: Muzzle Laser 05 Particle
category: particles
---

---

# Muzzle Laser 05 Particle

This document describes the `muzzle_laser_05.xml` particle effect, used for muzzle flashes in Noita.

## Sprite

The `Sprite` element defines the visual appearance of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_laser_05.png` - The texture file for the particle.
*   **offset_x**: `8` - Horizontal offset for the sprite.
*   **offset_y**: `7` - Vertical offset for the sprite.
*   **default_animation**: `muzzle` - The name of the animation to play by default.

## RectAnimation

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position of the animation frame within the sprite sheet.
*   **pos_y**: `0` - Starting Y position of the animation frame within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `16` - The width of each animation frame.
*   **frame_height**: `16` - The height of each animation frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no, 1 for yes). In this case, it does not loop.