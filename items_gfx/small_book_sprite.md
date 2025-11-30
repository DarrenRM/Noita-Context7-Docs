---
title: Small Book Sprite
category: items_gfx
---

# Small Book Sprite

This document describes the sprite definition for the "Small Book" item in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual representation of the item.

### Key Attributes:

*   **filename**: `data/items_gfx/book_small.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `5` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `6` - Vertical offset of the sprite's origin.

## Animation Definition

The `<RectAnimation>` element defines how the sprite animates.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `10` - The width of each individual frame.
*   **frame\_height**: `12` - The height of each individual frame.
*   **frame\_wait**: `0.23` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).