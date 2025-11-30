---
title: Blast Out Particle
category: particles
---

# Blast Out Particle

This document describes the `blast_out.xml` particle definition, used for visual effects in Noita.

## Sprite Definition

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/blast_out.png` - Specifies the texture file for the particle.
*   **offset\_x**: `32` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `32` - Vertical offset for the sprite's origin.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animation Definition

The `RectAnimation` element defines a specific animation sequence for the sprite.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `5` - The total number of frames in this animation.
*   **frame\_width**: `64` - The width of each individual frame.
*   **frame\_height**: `64` - The height of each individual frame.
*   **frame\_wait**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).