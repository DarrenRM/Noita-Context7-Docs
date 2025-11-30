---
title: Soul Particle
category: particles
---

---

# Soul Particle

This document describes the configuration for the "soul" particle in Noita, primarily focusing on its visual representation and animation.

## Sprite Configuration

The `Sprite` element defines the visual asset for the soul particle.

### Key Attributes:

*   **filename**: `data/particles/soul.png` - Specifies the texture file used for the particle.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `6` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The name of the animation to play by default.

## Animation Configuration

The `RectAnimation` element defines how the sprite is animated.

### Key Attributes for "stand" animation:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `4` - The total number of frames in the animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `12` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).