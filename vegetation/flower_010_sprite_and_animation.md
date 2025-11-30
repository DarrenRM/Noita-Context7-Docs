---
title: Flower 010 Sprite and Animation
category: data/vegetation
---

# Flower 010 Sprite and Animation

This document describes the sprite and animation data for `flower_010.xml`, a vegetation entity in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual appearance and initial positioning of the vegetation.

### Key Attributes:

*   **filename**: `data/vegetation/flower_010.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `44` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The name of the animation that plays by default.

## Animation Definition

The `<RectAnimation>` element defines the animation sequence for the vegetation.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation. This name is special and indicates a growing vegetation effect.
*   **pos\_x**: `0` - The starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - The starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `32` - The width of each individual animation frame.
*   **frame\_height**: `48` - The height of each individual animation frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).