---
title: Fire Particle Sprite
category: particles
---

---

# Fire Particle Sprite

This document describes the sprite definition for the fire particle in Noita.

## Sprite Definition

The `Sprite` element defines the visual appearance and animation of the fire particle.

### Key Attributes:

*   **filename**: `data/particles/fire.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `8` - The vertical offset of the sprite's origin.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animation: Explosion

The `RectAnimation` element defines the "explosion" animation.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `7` - The total number of frames in this animation.
*   **frame\_width**: `16` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.03` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no, 1 for yes). In this case, it does not loop.