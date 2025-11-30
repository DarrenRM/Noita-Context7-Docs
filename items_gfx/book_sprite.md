---
title: Book Sprite
category: items_gfx
---

---

# Book Sprite

This document describes the sprite definition for the "book" item in Noita.

## Sprite Definition

The core sprite for the book is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/book.png` - Specifies the image file used for the sprite.
*   **offset_x**: `8` - Horizontal offset for the sprite's position.
*   **offset_y**: `8` - Vertical offset for the sprite's position.

## Animation Definition

The book sprite utilizes a simple animation defined by the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos_x**: `0` - Starting X position within the sprite sheet.
*   **pos_y**: `0` - Starting Y position within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `16` - The width of each individual frame.
*   **frame_height**: `16` - The height of each individual frame.
*   **frame_wait**: `0.23` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).