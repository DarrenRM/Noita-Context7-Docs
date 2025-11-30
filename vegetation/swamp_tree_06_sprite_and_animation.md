---
title: Swamp Tree 06 Sprite and Animation
category: vegetation
---

---

# Swamp Tree 06 Sprite and Animation

This document describes the sprite and animation data for `swamp_tree_06.xml`, a vegetation asset in Noita.

## Sprite

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/swamp_tree_06.png` - The image file used for the sprite.
*   **offset_x**: `32` - Horizontal offset of the sprite's origin.
*   **offset_y**: `175` - Vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The animation that plays by default when this sprite is used.

## Animation: `vegetation_growth`

This animation is specifically designed for growing vegetation.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `64` - The width of each individual frame.
*   **frame_height**: `180` - The height of each individual frame.
*   **frame_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation will loop (1 for true, 0 for false).