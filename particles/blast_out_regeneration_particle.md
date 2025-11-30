---
title: Blast Out Regeneration Particle
category: particles
---

# Blast Out Regeneration Particle

This document describes the `blast_out_regeneration.xml` particle definition, used for visual effects in Noita.

## Sprite Definition

The primary visual component is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/blast_out.png` - Specifies the texture file used for the particle.
*   **offset\_x**, **offset\_y**: `32`, `32` - Defines the center point of the sprite relative to its origin.
*   **default\_animation**: `explosion` - Sets the default animation to play when the particle is spawned.
*   **color\_r**, **color\_g**, **color\_b**: `0.7`, `1`, `0.6` - Sets the base color tint of the sprite (Greenish-Yellow).

## Animation: Explosion

The `<RectAnimation>` tag defines the animation sequence for the particle.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**, **pos\_y**: `0`, `0` - The starting position of the animation frames within the sprite sheet.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: `64`, `64` - The dimensions of each individual frame.
*   **frame\_wait**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays once).