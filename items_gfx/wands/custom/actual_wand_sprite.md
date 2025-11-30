---
title: Actual Wand Sprite
category: items_gfx/wands/custom
---

# Actual Wand Sprite

This documentation describes the sprite definition for the "actual_wand" item in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual representation of the wand.

### Key Attributes:

*   **filename**: `data/items_gfx/wands/custom/actual_wand_honest.png`
    *   Specifies the path to the image file used for the sprite.

## RectAnimation Definition

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **name**: `default`
    *   The name of this animation state.
*   **pos_x**: `1`
    *   The starting X-coordinate of the sprite frame within the texture.
*   **pos_y**: `1`
    *   The starting Y-coordinate of the sprite frame within the texture.
*   **offset_x**: `4`
    *   The horizontal offset of the sprite's origin.
*   **offset_y**: `3`
    *   The vertical offset of the sprite's origin.
*   **frame_width**: `21`
    *   The width of a single animation frame.
*   **frame_height**: `9`
    *   The height of a single animation frame.
*   **has_offset**: `1`
    *   Indicates whether the `offset_x` and `offset_y` attributes are used.
*   **frame_count**: `1`
    *   The total number of frames in this animation.
*   **frame_wait**: `0.2`
    *   The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `10`
    *   The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0`
    *   Determines if the animation should loop (`1` for loop, `0` for no loop).