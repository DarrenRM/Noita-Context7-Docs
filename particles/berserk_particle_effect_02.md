---
title: Berserk Particle Effect 02
category: particles
---

# Berserk Particle Effect 02

This documentation describes the `berserk_02.xml` file, which defines a particle effect used in Noita. This specific particle appears to be a small, explosive visual effect.

## Sprite Definition

The primary visual component of this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/berserk_02.png` - Specifies the image file used for the particle's texture.
*   **offset\_x**: `2.5` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `2.5` - The vertical offset of the sprite's origin.
*   **default\_animation**: `explosion` - Sets the default animation to be played when this sprite is used.

## Animation Definition

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `explosion` - The name of this animation, referenced by the `default_animation` in the `<Sprite>` tag.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `5` - The width of each individual animation frame.
*   **frame\_height**: `5` - The height of each individual animation frame.
*   **frame\_wait**: `0.02` - The time in seconds to wait between displaying each frame.
*   **frames\_per\_row**: `1` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

This animation is very simple, consisting of a single frame, suggesting a static visual or a very quick burst effect.