---
title: Blast Out Charm Particle
category: particles
---

---

# Blast Out Charm Particle

This document describes the particle effect associated with the "Blast Out Charm" in Noita, focusing on its visual and animation properties for AI-assisted modding.

## Sprite Properties

The primary visual representation of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/blast_out.png` - Specifies the texture file used for the particle.
*   **offset\_x**: `32` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `32` - Vertical offset for the sprite's origin.
*   **default\_animation**: `explosion` - The name of the animation to be played by default.
*   **color\_r**: `1` - Red component of the particle's color (1.0 is full red).
*   **color\_g**: `0.7` - Green component of the particle's color (0.7 is 70% green).
*   **color\_b**: `0.95` - Blue component of the particle's color (0.95 is 95% blue).

## Animation Definition

The `<RectAnimation>` element defines the specific animation sequence for the particle.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation, referenced by `default_animation`.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `5` - The total number of frames in this animation.
*   **frame\_width**: `64` - The width of each individual animation frame.
*   **frame\_height**: `64` - The height of each individual animation frame.
*   **frame\_wait**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).