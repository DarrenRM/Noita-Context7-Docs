---
title: Shine Particle 08
category: particles
---

# Shine Particle 08

This documentation describes the `shine_08.xml` file, which defines a particle effect in Noita. This particle is a small, shimmering light effect.

## Sprite Definition

The primary element is the `<Sprite>` tag, which defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/shine_08.png` - Specifies the image file used for the particle's texture.
*   **offset\_x**: `2.5` - Horizontal offset for the sprite.
*   **offset\_y**: `2.5` - Vertical offset for the sprite.
*   **default\_animation**: `"explosion"` - Sets the default animation to be played when the particle is spawned.

## Animation Definition

The `<RectAnimation>` tag defines the animation sequence for the particle.

### Key Attributes:

*   **name**: `"explosion"` - The name of this animation, referenced by the `<Sprite>` tag.
*   **pos\_x**: `"0"` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `"6"` - The total number of frames in the animation.
*   **frame\_width**: `"5"` - The width of each individual animation frame.
*   **frame\_height**: `"5"` - The height of each individual animation frame.
*   **frame\_wait**: `"0.09"` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `"6"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop (1 for true, 0 for false).