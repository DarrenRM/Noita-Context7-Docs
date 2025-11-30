---
title: Muzzle Magic Large 05 Particle
category: particles
---

# Muzzle Magic Large 05 Particle

This document describes the configuration for the `muzzle_magic_large_05` particle effect in Noita, commonly used for muzzle flashes.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_large_05.png` - Specifies the texture file used for the particle.
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
*   **frame_width**: `16` - The width of each individual animation frame.
*   **frame_height**: `16` - The height of each individual animation frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).

This particle effect is a single, static frame intended for a quick muzzle flash.