---
title: Flower 06 Sprite and Animation
category: data
---

# Flower 06 Sprite and Animation

This document describes the sprite and animation data for `flower_06.xml`, a vegetation asset in Noita.

## Sprite Definition

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/flower_06.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `44` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The name of the animation that plays by default.

## Animation Definition: `vegetation_growth`

The `vegetation_growth` animation is a special type that creates a growing vegetation effect.

### Key Attributes:

*   **name**: `vegetation_growth` - Identifies this animation.
*   **pos\_x**: `0` - The X position of the animation's starting frame.
*   **pos\_y**: `0` - The Y position of the animation's starting frame.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `32` - The width of each individual frame.
*   **frame\_height**: `48` - The height of each individual frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).