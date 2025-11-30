---
title: Flower 05 Sprite and Animation
category: data/vegetation
---

# Flower 05 Sprite and Animation

This document describes the sprite and animation data for `flower_05.xml`, a vegetation entity in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual appearance and initial animation of the vegetation.

### Key Attributes:

*   **filename**: `data/vegetation/flower_05.png` - The path to the sprite image file.
*   **offset\_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `44` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - Specifies the animation to play by default. This is a special name that triggers a growing vegetation effect.

## Animation Definition

The `<RectAnimation>` tag defines the specific animation sequence.

### Key Attributes:

*   **name**: `vegetation_growth` - The name of this animation.
*   **pos\_x**: `0` - The X position of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - The Y position of the animation's top-left corner within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `32` - The width of each individual frame.
*   **frame\_height**: `48` - The height of each individual frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).

### Animation Notes:

The `vegetation_growth` animation is a special case in Noita. When assigned as the `default_animation` to a vegetation sprite, it signifies that this entity should exhibit a growing behavior. In this specific case, with `frame_count="1"`, it likely represents a single, static frame that is part of a larger, implicit growth sequence managed by the game engine.