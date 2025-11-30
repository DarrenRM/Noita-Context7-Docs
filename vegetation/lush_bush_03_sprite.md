---
title: Lush Bush 03 Sprite
category: data
---

# Lush Bush 03 Sprite

This document describes the sprite and animation data for `lush_bush_03.xml`, a vegetation asset in Noita.

## Sprite Definition

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/lush_bush_03.png` - The image file used for the sprite.
*   **offset\_x**: `24` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `46` - Vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - Specifies the default animation to play when the sprite is instantiated. This is a special name indicating a growing vegetation.

## Animation Data

The `vegetation_growth` animation is defined within the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `vegetation_growth` - The name of this animation.
*   **pos\_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `48` - The width of each individual frame.
*   **frame\_height**: `48` - The height of each individual frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).