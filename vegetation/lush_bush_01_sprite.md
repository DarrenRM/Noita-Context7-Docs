---
title: Lush Bush 01 Sprite
category: data
---

---

# Lush Bush 01 Sprite

This documentation describes the sprite and animation data for `lush_bush_01.xml`, a vegetation asset in Noita.

## Sprite Definition

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/lush_bush_01.png` - Specifies the image file used for the sprite.
*   **offset_x**: `24` - The horizontal offset of the sprite's origin.
*   **offset_y**: `46` - The vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The name of the animation that plays by default. This is a special name that triggers a growing vegetation effect.

## Animation Definition

The `vegetation_growth` animation is a special type that simulates the growth of vegetation.

### Key Attributes:

*   **name**: `vegetation_growth` - Identifies this animation.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `48` - The width of each individual frame.
*   **frame_height**: `48` - The height of each individual frame.
*   **frame_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).