---
title: Scroll Sprite Definition
category: items_gfx
---

# Scroll Sprite Definition

This document describes the sprite definition for the "scroll" item in Noita.

## Sprite Attributes

The primary sprite for the scroll is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/scroll.png` - Specifies the image file used for the sprite.
*   **offset_x**: `8` - Horizontal offset of the sprite's origin.
*   **offset_y**: `8` - Vertical offset of the sprite's origin.

## Animation Details

The scroll has a simple animation defined by the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `16` - The width of each individual frame.
*   **frame_height**: `16` - The height of each individual frame.
*   **frame_wait**: `0.23` - The time in seconds to wait before displaying the next frame.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).