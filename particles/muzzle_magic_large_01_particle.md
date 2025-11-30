---
title: Muzzle Magic Large 01 Particle
category: particles
---

# Muzzle Magic Large 01 Particle

This document describes the `muzzle_magic_large_01.xml` particle file, used for a large, magical muzzle flash effect in Noita.

## Sprite

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_large_01.png` - Specifies the texture file for the particle.
*   **offset_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset_y**: `7` - Vertical offset for the sprite's origin.
*   **default_animation**: `muzzle` - The name of the animation to play by default.

## RectAnimation

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation, referenced by `default_animation`.
*   **pos_x**: `0` - Starting X position of the animation frame within the sprite sheet.
*   **pos_y**: `0` - Starting Y position of the animation frame within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `16` - The width of each individual animation frame.
*   **frame_height**: `16` - The height of each individual animation frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).