---
title: Green Laser Muzzle Flash Particle
category: particles
---

---

# Green Laser Muzzle Flash Particle

This document describes the configuration for a green laser muzzle flash particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual component is a sprite.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_laser_green_01.png` - Specifies the texture file for the particle.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `7` - Vertical offset for the sprite's origin.
*   **default\_animation**: `muzzle` - The name of the animation to play by default.

## Animation Configuration

The sprite uses a `RectAnimation` to define its appearance over time.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation, referenced by `default_animation`.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation should not loop (play once).