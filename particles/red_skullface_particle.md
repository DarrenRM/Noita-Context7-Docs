---
title: Red Skullface Particle
category: particles
---

# Red Skullface Particle

This document describes the configuration for the "Red Skullface" particle effect in Noita, focusing on its visual representation and animation.

## Sprite Configuration

The primary visual element is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/skullface_red.png` - Specifies the image file used for the particle's texture.
*   **offset\_x**: `7.5` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `8` - The vertical offset of the sprite's origin.
*   **default\_animation**: `stand` - The name of the animation that plays by default when the particle is created.

## Animation: "stand"

The "stand" animation defines how the sprite cycles through its frames to create movement.

### Key Attributes:

*   **name**: `stand` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - The starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `8` - The total number of frames in this animation.
*   **frame\_width**: `15` - The width of each individual frame in pixels.
*   **frame\_height**: `16` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).