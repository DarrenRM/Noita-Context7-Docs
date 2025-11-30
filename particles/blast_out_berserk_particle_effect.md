---
title: Blast Out Berserk Particle Effect
category: particles
---

# Blast Out Berserk Particle Effect

This document describes the `blast_out_berserk.xml` particle effect, used for a berserk-related blast.

## Sprite

The primary visual representation of the particle.

### Key Attributes:

*   **filename**: `data/particles/blast_out.png` - The texture file used for the sprite.
*   **offset\_x**: `32` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `32` - Vertical offset of the sprite's origin.
*   **default\_animation**: `explosion` - The default animation to play.
*   **color\_r**: `1` - Red component of the sprite's color tint.
*   **color\_g**: `0.5` - Green component of the sprite's color tint.
*   **color\_b**: `0.5` - Blue component of the sprite's color tint.

## Animations

Defines the animations for the sprite.

### `explosion` Animation

*   **name**: `explosion`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `5` - Total number of frames in the animation.
*   **frame\_width**: `64` - Width of each animation frame.
*   **frame\_height**: `64` - Height of each animation frame.
*   **frame\_wait**: `0.02` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `5` - Number of frames in a single row of the sprite sheet.
*   **loop**: `0` - Whether the animation should loop (0 for no loop, 1 for loop).