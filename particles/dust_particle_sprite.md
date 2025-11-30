---
title: Dust Particle Sprite
category: particles
---

# Dust Particle Sprite

This document describes the sprite definition for the "dust" particle in Noita.

## Sprite Definition

The primary `<Sprite>` element defines the visual appearance and animation of the dust particle.

### Key Attributes:

*   **filename**: `data/particles/dust.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `1.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `1.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `explosion` - The name of the animation to play by default.

## Animations

The dust particle utilizes a single animation named "explosion".

### Explosion Animation (`<RectAnimation name="explosion">`)

This animation defines how the sprite frames are displayed.

#### Key Attributes:

*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `3` - The width of each individual frame.
*   **frame\_height**: `3` - The height of each individual frame.
*   **frame\_wait**: `0.02` - The time in seconds to wait between frames.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).