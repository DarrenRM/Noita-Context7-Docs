---
title: Lush Bush 02 Vegetation Sprite
category: data
---

# Lush Bush 02 Vegetation Sprite

This document describes the sprite and animation data for `lush_bush_02.xml`, a vegetation asset in Noita.

## Sprite Data

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/lush_bush_02.png` - Specifies the image file used for the sprite.
*   **offset_x**: `24` - The horizontal offset of the sprite's origin.
*   **offset_y**: `46` - The vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The name of the animation that plays by default.

## Animation Data

The `vegetation_growth` animation is a special type that creates a growing vegetation effect.

### Key Attributes for `vegetation_growth` RectAnimation:

*   **name**: `vegetation_growth` - Identifies this specific animation.
*   **pos_x**: `0` - The X position of the animation's starting frame within the sprite sheet.
*   **pos_y**: `0` - The Y position of the animation's starting frame within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `48` - The width of each individual frame.
*   **frame_height**: `48` - The height of each individual frame.
*   **frame_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation will loop (1 for true, 0 for false).