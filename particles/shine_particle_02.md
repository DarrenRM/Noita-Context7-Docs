---
title: Shine Particle 02
category: particles
---

# Shine Particle 02

This document describes the configuration for `shine_02.xml`, a particle effect in Noita.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/shine_02.png` - Specifies the image file used for the particle.
*   **offset\_x**: `2.5` - Horizontal offset for the sprite.
*   **offset\_y**: `2.5` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The default animation to play when the particle is spawned.

## Animation Details

The particle utilizes a `RectAnimation` for its visual effect.

### Animation: `explosion`

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `2` - The total number of frames in the animation.
*   **frame\_width**: `5` - The width of each individual frame.
*   **frame\_height**: `5` - The height of each individual frame.
*   **frame\_wait**: `0.05` - The time in seconds to wait between frames.
*   **frames\_per\_row**: `2` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).