---
title: Lush Bush 04 Vegetation Sprite
category: data
---

---

# Lush Bush 04 Vegetation Sprite

This documentation describes the sprite and animation data for `lush_bush_04.xml`, a vegetation entity in Noita.

## Sprite Information

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/lush_bush_04.png` - Specifies the image file used for the sprite.
*   **offset_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset_y**: `46` - The vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The name of the animation that plays by default. This is a special name indicating a growing vegetation.

## Animation Data

The animation for this vegetation is defined within the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos_x**: `0` - The X position of the animation's starting frame.
*   **pos_y**: `0` - The Y position of the animation's starting frame.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `32` - The width of each individual frame.
*   **frame_height**: `48` - The height of each individual frame.
*   **frame_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

**Note:** The `vegetation_growth` animation name is a special keyword in Noita that triggers a specific growing behavior for vegetation entities.