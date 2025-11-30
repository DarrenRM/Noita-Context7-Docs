---
title: Energy Shield Ring Particle
category: particles
---

# Energy Shield Ring Particle

This document describes the configuration for the "energy_shield_ring" particle effect in Noita, used for visual representation of energy shields.

## Sprite Configuration

The particle uses a sprite for its visual representation.

### Key Attributes:

*   **filename**: `data/particles/energy_shield_ring.png` - Specifies the image file for the particle's sprite.
*   **offset\_x**: `32` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `32` - The vertical offset of the sprite's origin.
*   **default\_animation**: `explosion` - The name of the default animation to play.

## Animation: Explosion

This section details the "explosion" animation used by the energy shield ring particle.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `64` - The width of each individual frame.
*   **frame\_height**: `64` - The height of each individual frame.
*   **frame\_wait**: `0.02` - The time in seconds to wait between frames.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).