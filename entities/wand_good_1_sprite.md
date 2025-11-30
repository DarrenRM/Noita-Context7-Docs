---
title: Wand Good 1 Sprite
category: entities
---

# Wand Good 1 Sprite

This document describes the sprite and animation data for the "Wand Good 1" item in Noita.

## Sprite

The primary sprite for this wand is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/items/wands/wand_good/wand_good_1.png` - Specifies the image file used for the sprite.
*   **offset_x**: `6` - Horizontal offset of the sprite.
*   **offset_y**: `3` - Vertical offset of the sprite.

## RectAnimation

The `<RectAnimation>` tag defines the animation for the sprite.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos_x**: `1` - Starting X position within the sprite sheet for the animation frame.
*   **pos_y**: `1` - Starting Y position within the sprite sheet for the animation frame.
*   **offset_x**: `3` - Horizontal offset applied during the animation.
*   **offset_y**: `4` - Vertical offset applied during the animation.
*   **has_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `12` - The width of each individual animation frame.
*   **frame_height**: `8` - The height of each individual animation frame.
*   **frame_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `10` - The number of frames that fit horizontally in a single row of the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).