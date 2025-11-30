---
title: Large Muzzle Flash 02 Particle
category: particles
---

---

# Large Muzzle Flash 02 Particle

This document describes the configuration for a large muzzle flash particle effect in Noita, specifically `muzzle_large_02.xml`.

## Sprite Configuration

The primary visual component of this particle is a sprite.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_large_02.png` - Specifies the image file used for the particle.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `7` - Vertical offset for the sprite's origin.
*   **default\_animation**: `muzzle` - The name of the animation to be played by default.

## Animation Configuration

This section defines the animation sequence for the muzzle flash.

### Key Attributes for `RectAnimation` (name="muzzle"):

*   **name**: `muzzle` - Identifies this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation should not loop (play only once).