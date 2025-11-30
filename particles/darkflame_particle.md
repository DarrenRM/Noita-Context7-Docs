---
title: Darkflame Particle
category: particles
---

---

# Darkflame Particle

This documentation describes the `darkflame.xml` particle definition, used for creating the visual effect of dark flames in Noita.

## Sprite Definition

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/darkflame.png` - Specifies the texture file used for the particle's sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `6` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The name of the animation to be played by default.

## Animation Definition

The `RectAnimation` element defines a specific animation sequence for the sprite.

### Key Attributes for `explosion` animation:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `7` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `12` - The height of each individual frame.
*   **frame\_wait**: `0.09` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).