---
title: Blast Out Telepathy Particle
category: particles
---

---

# Blast Out Telepathy Particle

This document describes the `blast_out_telepathy.xml` particle definition, used for visual effects in Noita.

## Sprite Definition

The primary visual component is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/blast_out.png` - Specifies the texture file used for the particle.
*   **offset\_x**, **offset\_y**: `32`, `32` - Defines the center point of the sprite.
*   **default\_animation**: `explosion` - Sets the initial animation to play.
*   **color\_r**, **color\_g**, **color\_b**: `1`, `0.8`, `0.4` - Sets the tint of the sprite to a reddish-orange.

## Animation: Explosion

The `<RectAnimation>` tag defines the animation sequence for the particle.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**, **pos\_y**: `0`, `0` - The starting position of the animation frames within the sprite sheet.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: `64`, `64` - The dimensions of each individual frame.
*   **frame\_wait**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `5` - Indicates how many frames are arranged horizontally in the sprite sheet.
*   **loop**: `0` - Specifies that the animation does not loop (plays once).