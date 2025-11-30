---
title: Scepter 01 Sprite and Animation
category: items_gfx
---

# Scepter 01 Sprite and Animation

This document details the sprite and animation data for the `scepter_01` item in Noita.

## Sprite Definition

The primary sprite for `scepter_01` is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/wands/custom/scepter_01.png`
    *   Specifies the path to the image file used for the sprite.

## RectAnimation Definition

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **name**: `default`
    *   The name of this animation state.
*   **pos_x**: `1`
    *   The starting X position within the sprite sheet.
*   **pos_y**: `1`
    *   The starting Y position within the sprite sheet.
*   **offset_x**: `3`
    *   Horizontal offset for the sprite's origin.
*   **offset_y**: `4`
    *   Vertical offset for the sprite's origin.
*   **frame_width**: `19`
    *   The width of each individual animation frame.
*   **frame_height**: `11`
    *   The height of each individual animation frame.
*   **has_offset**: `1`
    *   Indicates that the `offset_x` and `offset_y` attributes are used.
*   **frame_count**: `1`
    *   The total number of frames in the animation.
*   **frame_wait**: `0.2`
    *   The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `10`
    *   The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0`
    *   Indicates whether the animation should loop (0 for no loop, 1 for loop).