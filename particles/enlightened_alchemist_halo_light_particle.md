---
title: Enlightened Alchemist Halo Light Particle
category: particles
---

# Enlightened Alchemist Halo Light Particle

This document describes the `enlightened_alchemist_halo_light.xml` particle definition, used for visual effects in Noita.

## Sprite Definition

The particle utilizes a sprite for its visual representation.

### Sprite Attributes

*   **filename**: `data/particles/enlightened_alchemist_halo_light.png` - The image file used for the particle.
*   **offset\_x**: `21` - Horizontal offset for the sprite.
*   **offset\_y**: `44` - Vertical offset for the sprite.
*   **default\_animation**: `stand` - The animation to play by default.

### Animation: `stand`

This defines the animation sequence for the sprite.

*   **name**: `stand`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - Total number of frames in the animation.
*   **frame\_width**: `42` - Width of each individual frame.
*   **frame\_height**: `38` - Height of each individual frame.
*   **frame\_wait**: `0.04` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `1` - Number of frames in a single row of the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).