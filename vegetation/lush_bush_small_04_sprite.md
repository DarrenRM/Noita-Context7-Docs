---
title: Lush Bush Small 04 Sprite
category: data
---

---

# Lush Bush Small 04 Sprite

This document describes the sprite and animation data for the `lush_bush_small_04` vegetation entity in Noita.

## Sprite Definition

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/lush_bush_small_04.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `30` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The name of the animation that plays by default. This is a special name indicating a growing vegetation.

## Animation Definition

The `vegetation_growth` animation is defined within the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos\_x**: `0` - The X position of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - The Y position of the animation's top-left corner within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `32` - The width of each individual frame.
*   **frame\_height**: `32` - The height of each individual frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).