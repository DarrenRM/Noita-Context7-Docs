---
title: Muzzle Flash Medium 04 Particle
category: particles
---

# Muzzle Flash Medium 04 Particle

This document describes the configuration for a muzzle flash particle effect in Noita, specifically `muzzle_medium_04.xml`.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_medium_04.png` - Specifies the texture file used for the particle.
*   **offset_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset_y**: `7` - The vertical offset of the sprite's origin.
*   **default_animation**: `muzzle` - The name of the default animation to play.

## Animation Configuration

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation.
*   **pos_x**: `0` - The starting X position of the animation frame within the sprite sheet.
*   **pos_y**: `0` - The starting Y position of the animation frame within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `16` - The width of each animation frame.
*   **frame_height**: `16` - The height of each animation frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).