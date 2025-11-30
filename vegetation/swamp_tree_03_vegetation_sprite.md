---
title: Swamp Tree 03 Vegetation Sprite
category: data/vegetation
---

---

# Swamp Tree 03 Vegetation Sprite

This document describes the sprite data for `swamp_tree_03.xml`, a vegetation asset in Noita.

## Sprite Definition

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/swamp_tree_03.png` - Specifies the image file for the sprite.
*   **offset_x**: `32` - The horizontal offset of the sprite's origin.
*   **offset_y**: `175` - The vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The animation to play by default when this sprite is used.

## Animation: `vegetation_growth`

This is a special animation name used for growing vegetation.

### Key Attributes:

*   **name**: `vegetation_growth`
*   **pos_x**: `0` - The X position of the animation's starting frame.
*   **pos_y**: `0` - The Y position of the animation's starting frame.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `64` - The width of each individual frame.
*   **frame_height**: `180` - The height of each individual frame.
*   **frame_wait**: `1.0` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).