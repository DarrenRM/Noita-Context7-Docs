---
title: Desert Eagle Sprite and Animation
category: items_gfx
---

---

# Desert Eagle Sprite and Animation

This document describes the sprite and animation data for the "Desert Eagle" item in Noita.

## Sprite

The `Sprite` element defines the visual representation of the item.

### Key Attributes:

*   **filename**: `data/items_gfx/desert_eagle.png` - The path to the image file used for the sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite's position.
*   **offset\_y**: `3` - Vertical offset for the sprite's position.

## RectAnimation

The `RectAnimation` element defines the animation for the sprite.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `1` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `1` - Starting Y position within the sprite sheet for the animation.
*   **offset\_x**: `3` - Horizontal offset specific to this animation frame.
*   **offset\_y**: `4` - Vertical offset specific to this animation frame.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are used.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `13` - The width of each individual frame.
*   **frame\_height**: `7` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop.