---
title: Flower 04 Sprite and Animation
category: data/vegetation
---

# Flower 04 Sprite and Animation

This document describes the sprite and animation data for `flower_04.xml`, a vegetation asset in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual representation and initial animation for the vegetation.

### Key Attributes:

*   **filename**: `data/vegetation/flower_04.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `44` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The name of the animation to play by default. This is a special name that triggers a growing vegetation effect.

## Animation Definition

The `<RectAnimation>` tag defines the specific animation sequence for the sprite.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `32` - The width of each individual frame.
*   **frame\_height**: `48` - The height of each individual frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).