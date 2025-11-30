---
title: Blue Poof Explosion Particle
category: particles
---

---

# Blue Poof Explosion Particle

This document describes the configuration for a blue poof explosion particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/particles/explosion_040_poof_blue.png` - Specifies the image file used for the particle's sprite.
*   **offset\_x**: `20` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `20` - Vertical offset for the sprite's origin.
*   **default\_animation**: `explosion` - The name of the animation to be played by default.

## Animation Details

The `<RectAnimation>` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `40` - The width of each individual frame in pixels.
*   **frame\_height**: `40` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.04` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).