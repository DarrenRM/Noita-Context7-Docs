---
title: Drunk Particle
category: particles
---

---

# Drunk Particle

This documentation describes the `drunk.xml` particle definition for Noita, focusing on its visual representation and animation.

## Sprite

The `Sprite` element defines the visual appearance of the particle.

### Key Attributes:

*   **filename**: `data/particles/drunk.png` - Specifies the texture file used for the particle's sprite.
*   **offset\_x**: `3.5` - Horizontal offset for the sprite.
*   **offset\_y**: `3.5` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The name of the animation to play by default.

## Animations

The `RectAnimation` element defines how the sprite is animated.

### `stand` Animation

This animation is used for the default "stand" state of the drunk particle.

#### Key Attributes:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet.
*   **frame\_count**: `"8"` - The total number of frames in the animation.
*   **frame\_width**: `"7"` - The width of each individual frame.
*   **frame\_height**: `"7"` - The height of each individual frame.
*   **frame\_wait**: `"0.07"` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `"8"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop continuously.