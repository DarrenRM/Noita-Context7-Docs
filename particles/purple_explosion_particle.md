---
title: Purple Explosion Particle
category: particles
---

---

# Purple Explosion Particle

This document describes the configuration for the "purple_explosion" particle effect in Noita, focusing on its visual representation and animation.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/purple_explosion.png` - Specifies the image file used for the particle's visual.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `6` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - Sets the default animation to be played for this sprite.

## Animation Details

The animation for the purple explosion is defined using the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `explosion` - The name of this animation, referenced by the sprite.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `12` - The width of each individual animation frame.
*   **frame\_height**: `12` - The height of each individual animation frame.
*   **frame\_wait**: `0.04` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `5` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).