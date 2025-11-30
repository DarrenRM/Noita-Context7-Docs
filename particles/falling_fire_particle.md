---
title: Falling Fire Particle
category: particles
---

# Falling Fire Particle

This document describes the configuration for the "falling fire" particle effect in Noita, primarily focusing on its visual representation and animation.

## Sprite Configuration

The `Sprite` element defines the visual asset used for the particle.

### Key Attributes:

*   **filename**: `data/particles/fire_falling.png` - Specifies the image file containing the particle's sprite sheet.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `11` - Vertical offset for the sprite's origin.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animation Details

The `RectAnimation` element defines how the sprite sheet is used to create an animation.

### Key Attributes:

*   **name**: `explosion` - The identifier for this specific animation.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `12` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.06` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `12` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).