---
title: Berserk Particle Effect 04
category: particles
---

---

# Berserk Particle Effect 04

This document describes the configuration for a particle effect named "berserk_04", likely used to represent a berserk-related visual in Noita.

## Sprite Configuration

The primary visual representation of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/berserk_04.png` - Specifies the image file used for the particle's texture.
*   **offset\_x**: `2.5` - Horizontal offset for the sprite.
*   **offset\_y**: `2.5` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - Sets the default animation to be played.

## Animation Details

The particle utilizes a single animation named "explosion".

### Key Attributes for `RectAnimation` (name="explosion"):

*   **pos\_x**: `0` - Starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `5` - The width of each individual animation frame.
*   **frame\_height**: `5` - The height of each individual animation frame.
*   **frame\_wait**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

This configuration suggests a very simple, single-frame animation that likely plays once and then the particle disappears or transitions.