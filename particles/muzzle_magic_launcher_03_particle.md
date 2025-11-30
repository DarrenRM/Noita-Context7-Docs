---
title: Muzzle Magic Launcher 03 Particle
category: particles
---

---

# Muzzle Magic Launcher 03 Particle

This document describes the configuration for the "muzzle_magic_launcher_03" particle effect in Noita, commonly used for muzzle flashes.

## Sprite Configuration

The primary visual component of this particle is a sprite.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_launcher_03.png` - Specifies the image file used for the particle.
*   **offset\_x**: `8` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `7` - Vertical offset of the sprite's origin.
*   **default\_animation**: `muzzle` - The name of the animation to play by default.

## Animation Configuration

This section defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).