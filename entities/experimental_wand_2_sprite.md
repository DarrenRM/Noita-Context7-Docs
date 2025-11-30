---
title: Experimental Wand 2 Sprite
category: entities
---

# Experimental Wand 2 Sprite

This document details the sprite and animation data for the "Experimental Wand 2" item in Noita.

## Sprite

The primary sprite for this wand is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/items/wands/experimental/experimental_wand_2.png` - Specifies the image file used for the sprite.

## RectAnimation

This tag defines the animation sequence for the wand's sprite.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos_x**: `0` - The starting X coordinate of the sprite frame within the texture.
*   **pos_y**: `0` - The starting Y coordinate of the sprite frame within the texture.
*   **offset_x**: `3` - Horizontal offset for the sprite's position.
*   **offset_y**: `4` - Vertical offset for the sprite's position.
*   **has_offset**: `1` - Indicates that an offset is applied.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `14` - The width of each individual animation frame.
*   **frame_height**: `8` - The height of each individual animation frame.
*   **frame_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Specifies that the animation does not loop.