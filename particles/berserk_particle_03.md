---
title: Berserk Particle 03
category: particles
---

---

# Berserk Particle 03

This document describes the configuration for a particle effect in Noita, specifically `berserk_03.xml`. This particle appears to be a small, explosive visual effect.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/berserk_03.png` - Specifies the image file used for the particle's texture.
*   **offset\_x**: `2.5` - Horizontal offset for the sprite.
*   **offset\_y**: `2.5` - Vertical offset for the sprite.
*   **default\_animation**: `explosion` - Sets the default animation to be played when the particle is spawned.

## Animation Configuration

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **name**: `explosion` - The name of this animation, referenced by `default_animation`.
*   **pos\_x**: `0` - Starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `5` - The width of each individual animation frame.
*   **frame\_height**: `5` - The height of each individual animation frame.
*   **frame\_wait**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

This particle uses a single frame animation, suggesting a static visual effect or a very brief burst.