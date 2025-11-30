---
title: Big Green Orb Outgoing Particle
category: particles
---

---

# Big Green Orb Outgoing Particle

This document describes the particle effect used for the "big green orb outgoing" visual in Noita. It defines the sprite and its animation.

## Sprite Definition

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/orb_green_big_out.png` - Specifies the image file used for the particle's visual.
*   **offset\_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `8` - The vertical offset of the sprite's origin.
*   **default\_animation**: `explosion` - The name of the animation that plays by default.

## Animation: Explosion

The `<RectAnimation>` tag defines the "explosion" animation.

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `10` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame in pixels.
*   **frame\_height**: `16` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.025` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).