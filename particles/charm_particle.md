---
title: Charm Particle
category: particles
---

# Charm Particle

This document describes the configuration for the "charm" particle effect in Noita, focusing on its visual representation and animation.

## Sprite Configuration

The `Sprite` element defines the visual asset used for the particle.

### Key Attributes:

*   **filename**: `data/particles/charm.png` - Specifies the image file used for the particle's texture.
*   **offset\_x**: `3.5` - Horizontal offset for the sprite.
*   **offset\_y**: `3` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The name of the animation to be used by default.

## Animation Configuration

The `RectAnimation` element defines how the sprite is animated.

### Key Attributes for "stand" animation:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet.
*   **frame\_count**: `"1"` - The total number of frames in this animation.
*   **frame\_width**: `"7"` - The width of each individual frame.
*   **frame\_height**: `"6"` - The height of each individual frame.
*   **frame\_wait**: `"0.12"` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `"6"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop (1 for true, 0 for false).