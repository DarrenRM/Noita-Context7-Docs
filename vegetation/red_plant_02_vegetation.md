---
title: Red Plant 02 Vegetation
category: vegetation
---

---

# Red Plant 02 Vegetation

This document describes the `redplant_02.xml` file, which defines a specific type of vegetation in Noita.

## Sprite Definition

The primary visual representation of this vegetation is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/vegetation/redplant_02.png` - Specifies the image file used for the sprite.
*   **offset_x**: `7` - Horizontal offset of the sprite's origin.
*   **offset_y**: `11` - Vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The animation that plays by default when this vegetation is spawned.

## Animation Definition

The `vegetation_growth` animation is a special type of animation in Noita that signifies a growing vegetation entity.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `14` - The width of each individual frame.
*   **frame_height**: `12` - The height of each individual frame.
*   **frame_wait**: `999.0` - The duration (in frames) each frame is displayed. A high value indicates a slow or static animation.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).