---
title: Swamp Tree 04 Sprite
category: data/vegetation
---

---

# Swamp Tree 04 Sprite

This document describes the sprite and animation data for `swamp_tree_04.xml`, a vegetation asset in Noita.

## Sprite Data

The primary sprite information is defined within the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/swamp_tree_04.png` - The image file used for the sprite.
*   **offset_x**: `32` - Horizontal offset of the sprite's origin.
*   **offset_y**: `175` - Vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The animation to play by default.

## Animation Data

The `vegetation_growth` animation is a special type that handles the growing effect for vegetation.

### Key Attributes for `vegetation_growth`:

*   **name**: `vegetation_growth` - Identifies this as the special vegetation growth animation.
*   **pos_x**: `0` - X-position of the animation's starting frame.
*   **pos_y**: `0` - Y-position of the animation's starting frame.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `64` - The width of each individual frame.
*   **frame_height**: `180` - The height of each individual frame.
*   **frame_wait**: `1.0` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).