---
title: Icy Smoke Particle
category: particles
---

---

# Icy Smoke Particle

This document describes the configuration for the "icy smoke" particle effect in Noita, used for visual representation of cold or icy phenomena.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/smoke_icy.png` - Specifies the texture file used for the particle sprite.
*   **offset\_x**: `8.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `8` - Vertical offset for the sprite's origin.
*   **default\_animation**: `smoke` - The name of the animation to be played by default.

## Animation Details

The `RectAnimation` element defines the specific animation sequence for the "smoke" effect.

### Key Attributes:

*   **name**: `smoke` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `8` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.03` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).