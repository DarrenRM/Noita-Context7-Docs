---
title: Ceiling Bush 01 Sprite
category: data
---

---

# Ceiling Bush 01 Sprite

This documentation describes the sprite and animation data for `ceiling_bush_01.xml`, a vegetation entity in Noita.

## Sprite

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/ceiling_bush_01.png` - The image file used for the sprite.
*   **offset_x**: `36` - Horizontal offset of the sprite's origin.
*   **offset_y**: `30` - Vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The name of the animation that plays by default.

## Animation: `vegetation_growth`

This animation is specifically designed for growing vegetation.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos_x**: `0` - X-position of the animation's starting frame.
*   **pos_y**: `0` - Y-position of the animation's starting frame.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `72` - The width of each animation frame.
*   **frame_height**: `48` - The height of each animation frame.
*   **frame_wait**: `1.0` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation will loop (1 for true, 0 for false).