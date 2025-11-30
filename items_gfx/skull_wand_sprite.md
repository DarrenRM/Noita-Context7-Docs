---
title: Skull Wand Sprite
category: items_gfx
---

# Skull Wand Sprite

This document describes the sprite definition for the "skull_01" wand in Noita.

## Sprite Definition

The core of this definition is the `<Sprite>` tag, which points to the image file used for the wand's visual representation.

### Key Attributes:

*   **filename**: `data/items_gfx/wands/custom/skull_01.png` - The path to the sprite image file.

## RectAnimation Definition

The `<RectAnimation>` tag defines how the sprite is animated. For this wand, it's a simple, non-looping animation.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos_x**, **pos_y**: `1`, `1` - The starting X and Y coordinates within the sprite sheet for the animation frames.
*   **offset_x**, **offset_y**: `3`, `4` - The offset of the sprite's origin from its top-left corner.
*   **frame_width**, **frame_height**: `19`, `11` - The dimensions of each individual animation frame.
*   **has_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are used.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Specifies that the animation does not loop (it plays once).