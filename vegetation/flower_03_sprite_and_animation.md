---
title: Flower 03 Sprite and Animation
category: data/vegetation
---

# Flower 03 Sprite and Animation

This document describes the sprite and animation data for `flower_03.xml`, a vegetation asset in Noita.

## Sprite

The `Sprite` element defines the visual appearance and initial positioning of the flower.

### Key Attributes:

*   **filename**: `data/vegetation/flower_03.png` - The path to the sprite image file.
*   **offset_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset_y**: `44` - The vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - Specifies the animation to play by default.

## Animation: `vegetation_growth`

The `vegetation_growth` animation is a special type of animation in Noita that handles the growth of vegetation.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos_x**: `0` - The starting X position of the animation frames.
*   **pos_y**: `0` - The starting Y position of the animation frames.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `32` - The width of each animation frame.
*   **frame_height**: `48` - The height of each animation frame.
*   **frame_wait**: `1.0` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).