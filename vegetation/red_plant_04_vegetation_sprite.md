---
title: Red Plant 04 Vegetation Sprite
category: data
---

---

# Red Plant 04 Vegetation Sprite

This documentation describes the sprite and animation data for `redplant_04.xml`, a vegetation asset in Noita.

## Sprite

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/redplant_04.png` - Specifies the image file used for the sprite.
*   **offset_x**: `7` - Horizontal offset of the sprite's origin.
*   **offset_y**: `11` - Vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The name of the animation that plays by default.

## Animation: `vegetation_growth`

This animation is a special type used for growing vegetation.

### Key Attributes:

*   **name**: `vegetation_growth` - Identifies this as the special growing vegetation animation.
*   **pos_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `14` - The width of each individual frame.
*   **frame_height**: `12` - The height of each individual frame.
*   **frame_wait**: `999.0` - The duration (in game ticks) each frame is displayed. A high value indicates a slow or static appearance.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).