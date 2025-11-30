---
title: Muzzle Magic Launcher Large 04 Particle
category: particles
---

# Muzzle Magic Launcher Large 04 Particle

This document describes the configuration for a muzzle flash particle effect in Noita, specifically `muzzle_magic_launcher_large_04`.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_launcher_large_04.png` - Specifies the image file used for the particle.
*   **offset\_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `7` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"muzzle"` - The name of the animation to be used by default.

## Animation Details

The particle utilizes a single animation named "muzzle" for its visual representation.

### Key Attributes:

*   **name**: `"muzzle"` - The identifier for this animation.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame in pixels.
*   **frame\_height**: `16` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).