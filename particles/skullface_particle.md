---
title: Skullface Particle
category: particles
---

---

# Skullface Particle

This document describes the configuration for the "skullface" particle in Noita, focusing on its visual representation and animation.

## Sprite Configuration

The `Sprite` element defines the visual asset and its initial properties.

### Key Attributes:

*   **filename**: `data/particles/skullface.png` - Specifies the image file used for the particle's texture.
*   **offset\_x**: `7.5` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `8` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"stand"` - The name of the animation to play by default when the particle is created.

## Animation: "stand"

The `RectAnimation` element defines a specific animation sequence for the sprite.

### Key Attributes:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `"0"` - The starting X position within the sprite sheet for this animation.
*   **pos\_y**: `"0"` - The starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `"8"` - The total number of frames in this animation.
*   **frame\_width**: `"15"` - The width of each individual frame in pixels.
*   **frame\_height**: `"16"` - The height of each individual frame in pixels.
*   **frame\_wait**: `"0.12"` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `"8"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates whether the animation should loop (1 for true, 0 for false).

This animation likely represents a "standing" or idle animation for the skullface particle, cycling through 8 frames with a slight delay between each.