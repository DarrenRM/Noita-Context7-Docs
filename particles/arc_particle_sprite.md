---
title: Arc Particle Sprite
category: particles
---

---

# Arc Particle Sprite

This document describes the sprite definition for the "arc" particle in Noita.

## Sprite Definition

The primary sprite definition for the arc particle is handled by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/arc.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `6` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `6` - The vertical offset of the sprite's origin.
*   **default\_animation**: `explosion` - The name of the default animation to play for this sprite.

## Animations

The sprite can have multiple animations defined. The "explosion" animation is specified as the default.

### Explosion Animation (`<RectAnimation name="explosion">`)

This animation defines the sequence of frames for the explosion effect.

#### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `8` - The total number of frames in the animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `12` - The height of each individual frame.
*   **frame\_wait**: `0.04` - The time in seconds to wait between each frame.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).