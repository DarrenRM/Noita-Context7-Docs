---
title: Smoke Particle 04
category: particles
---

---

# Smoke Particle 04

This document describes the configuration for a smoke particle effect, specifically `smoke_04.xml`.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/smoke_04.png` - Specifies the texture file used for the particle.
*   **offset\_x**: `20` - Horizontal offset for the sprite.
*   **offset\_y**: `20` - Vertical offset for the sprite.
*   **default\_animation**: `smoke` - The name of the default animation to play.

## Animation Configuration

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `smoke` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `40` - The width of each individual frame.
*   **frame\_height**: `40` - The height of each individual frame.
*   **frame\_wait**: `0.05` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).