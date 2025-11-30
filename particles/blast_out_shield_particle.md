---
title: Blast Out Shield Particle
category: particles
---

---

# Blast Out Shield Particle

This document describes the `blast_out_shield.xml` particle effect, used for visual feedback when a shield is broken or a blast occurs.

## Sprite

The primary visual component of the particle.

### Key Attributes:

*   **filename**: `data/particles/blast_out.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `32` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `32` - Vertical offset for the sprite's origin.
*   **default\_animation**: `explosion` - The animation to play by default.
*   **color\_r**: `0.7` - Red component of the sprite's color tint.
*   **color\_g**: `0.95` - Green component of the sprite's color tint.
*   **color\_b**: `1` - Blue component of the sprite's color tint.

## Animations

Defines the sequences of frames that make up the visual effect.

### explosion

This animation represents the core visual of the blast.

#### Key Attributes:

*   **name**: `explosion` - Identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `64` - The width of each individual frame.
*   **frame\_height**: `64` - The height of each individual frame.
*   **frame\_wait**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation should not loop (play only once).