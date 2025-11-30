---
title: Bush Growth Animation
category: data
---

---

# Bush Growth Animation

This document describes the animation data for a growing bush in Noita, as defined in `bush_growth_1.xml`.

## Sprite Definition

The primary sprite for this animation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/bush_growth_1.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `12` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `31` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - Sets the default animation to play for this sprite. This is a special name that triggers vegetation growth.

## Animation Data

The animation itself is defined using the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `vegetation_growth` - The name of the animation. This matches the `default_animation` in the `<Sprite>` tag.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `6` - The total number of frames in the animation.
*   **frame\_width**: `32` - The width of each individual animation frame.
*   **frame\_height**: `34` - The height of each individual animation frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

This configuration defines a growing bush animation that plays over 6 frames, each 32x34 pixels, with a 1-second delay between frames, and loops continuously.