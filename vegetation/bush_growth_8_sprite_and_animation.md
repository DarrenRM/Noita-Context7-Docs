---
title: Bush Growth 8 Sprite and Animation
category: data/vegetation
---

# Bush Growth 8 Sprite and Animation

This document describes the sprite and animation data for `bush_growth_8.xml`, a visual asset used for growing vegetation in Noita.

## Sprite Information

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/bush_growth_8.png` - Specifies the image file for the sprite.
*   **offset\_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `33` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The name of the animation to be played by default. This is a special name that indicates the creation of a growing vegetation entity.

## Animation Data

The animation details are provided within the `<RectAnimation>` tag, named `vegetation_growth`.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos\_x**: `0` - The X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - The Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `32` - The width of each individual animation frame.
*   **frame\_height**: `34` - The height of each individual animation frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `6` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).