---
title: Electrocution Blast Particle
category: particles
---

# Electrocution Blast Particle

This document describes the particle effect used for an electrocution blast in Noita.

## Sprite

The visual representation of the particle is defined by a `Sprite` element.

### Key Attributes:

*   **filename**: `data/particles/blast_out.png` - The texture file used for the sprite.
*   **offset\_x**, **offset\_y**: `32`, `32` - The center offset of the sprite.
*   **default\_animation**: `explosion` - The default animation to play.
*   **color\_r**, **color\_g**, **color\_b**: `0.6`, `0.9`, `1` - The RGB color tint applied to the sprite, giving it a bluish-white appearance.

## Animation

The `explosion` animation defines how the sprite animates.

### Key Attributes:

*   **name**: `explosion` - The name of this animation.
*   **pos\_x**, **pos\_y**: `0`, `0` - The starting position of the animation frames within the sprite sheet.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: `64`, `64` - The dimensions of each individual frame.
*   **frame\_wait**: `0.02` - The time in seconds each frame is displayed before advancing.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays once).