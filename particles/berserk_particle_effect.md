---
title: Berserk Particle Effect
category: particles
---

---

# Berserk Particle Effect

This document describes the `berserk_01.xml` particle effect, used to visually represent the berserk status in Noita.

## Sprite

The primary visual component of the particle.

### Key Attributes:

*   **filename**: `data/particles/berserk_01.png` - Specifies the texture file for the particle.
*   **offset\_x**: `2.5` - Horizontal offset for the sprite.
*   **offset\_y**: `2.5` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - The animation to play by default.

## Animations

Defines the visual sequences for the particle.

### `explosion` Animation

This animation is used for the berserk particle.

#### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `5` - The width of each individual frame.
*   **frame\_height**: `5` - The height of each individual frame.
*   **frame\_wait**: `0.02` - The time in seconds to wait between frames.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).