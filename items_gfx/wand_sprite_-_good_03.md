---
title: Wand Sprite - good_03
category: items_gfx
---

# Wand Sprite - good_03

This document describes the sprite definition for the `good_03` wand in Noita.

## Sprite Definition

The core of this definition is the `<Sprite>` tag, which points to the visual asset for the wand.

### Key Attributes

*   **`filename`**: Specifies the path to the sprite image file.
    *   `data/items_gfx/wands/custom/good_03.png`

## RectAnimation Definition

The `<RectAnimation>` tag defines how the sprite is rendered and animated.

### Key Attributes

*   **`name`**: The name of the animation state.
    *   `default`
*   **`pos_x`, `pos_y`**: The starting X and Y coordinates within the sprite sheet for the animation.
    *   `pos_x="1"`
    *   `pos_y="1"`
*   **`offset_x`, `offset_y`**: The offset applied to the sprite's position.
    *   `offset_x="3"`
    *   `offset_y="4"`
*   **`frame_width`, `frame_height`**: The dimensions of each individual frame in the animation.
    *   `frame_width="23"`
    *   `frame_height="9"`
*   **`has_offset`**: Indicates if the `offset_x` and `offset_y` attributes are used.
    *   `has_offset="1"` (True)
*   **`frame_count`**: The total number of frames in the animation.
    *   `frame_count="1"`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed.
    *   `frame_wait="0.2"`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `frames_per_row="10"`
*   **`loop`**: Determines if the animation should loop.
    *   `loop="0"` (False - plays once)