---
title: Machinegun Sprite and Animation
category: items_gfx
---

# Machinegun Sprite and Animation

This document describes the sprite and animation data for the "machinegun" item in Noita.

## Sprite

The primary sprite for the machinegun is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/machinegun.png` - Specifies the image file used for the sprite.
*   **offset_x**: `6` - Horizontal offset of the sprite.
*   **offset_y**: `3` - Vertical offset of the sprite.

## RectAnimation

The `<RectAnimation>` tag defines the animation sequence for the machinegun.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos_x**: `1` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `1` - Starting Y position within the sprite sheet for the animation.
*   **offset_x**: `3` - Horizontal offset for the animation frame.
*   **offset_y**: `4` - Vertical offset for the animation frame.
*   **has_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are used.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `15` - The width of each animation frame.
*   **frame_height**: `7` - The height of each animation frame.
*   **frame_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).