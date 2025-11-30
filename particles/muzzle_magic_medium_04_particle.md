---
title: Muzzle Magic Medium 04 Particle
category: particles
---

---

# Muzzle Magic Medium 04 Particle

This document describes the configuration for the "Muzzle Magic Medium 04" particle effect in Noita, commonly used for muzzle flashes.

## Sprite Configuration

The primary visual component of this particle is a sprite.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_medium_04.png` - The image file used for the particle.
*   **offset\_x**: `8` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `7` - Vertical offset of the sprite's origin.
*   **default\_animation**: `muzzle` - The name of the animation to play by default.

## Animation Configuration

This particle uses a simple, non-looping animation.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (0 for false, 1 for true).