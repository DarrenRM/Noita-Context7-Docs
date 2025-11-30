---
title: Lush Bush Small 03 Sprite
category: data/vegetation
---

---

# Lush Bush Small 03 Sprite

This documentation describes the sprite and animation data for the `lush_bush_small_03` vegetation entity in Noita.

## Sprite Information

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/lush_bush_small_03.png` - Specifies the image file used for the sprite.
*   **offset_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset_y**: `30` - The vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The name of the animation that plays by default. This is a special name indicating a growing vegetation effect.

## Animation Data

The `vegetation_growth` animation is defined within the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos_x**: `0` - The starting X position of the animation frame within the sprite sheet.
*   **pos_y**: `0` - The starting Y position of the animation frame within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `32` - The width of each individual frame.
*   **frame_height**: `32` - The height of each individual frame.
*   **frame_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).