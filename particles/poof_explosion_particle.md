---
title: Poof Explosion Particle
category: particles
---

# Poof Explosion Particle

This document describes the `explosion_040_poof.xml` file, which defines a visual particle effect for a "poof" explosion in Noita.

## Sprite Definition

The primary visual component is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/explosion_040_poof.png` - Specifies the image file used for the particle's texture.
*   **offset\_x**: `20` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `20` - Vertical offset for the sprite's origin.
*   **default\_animation**: `explosion` - Sets the default animation to be played.

## Animation Definition

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **name**: `explosion` - The name of this animation, referenced by the `<Sprite>` tag.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `40` - The width of each individual frame.
*   **frame\_height**: `40` - The height of each individual frame.
*   **frame\_wait**: `0.04` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays once).