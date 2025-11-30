---
title: Material Backbag Sprite
category: items_gfx
---

---

# Material Backbag Sprite

This document describes the sprite definition for the "material_backbag" item in Noita.

## Sprite Definition

The primary sprite for the material backbag is defined by the `<Sprite>` tag.

### Key Attributes

*   **filename**: `data/items_gfx/material_backbag.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `4.5` - Horizontal offset for the sprite's anchor point.
*   **offset\_y**: `5.5` - Vertical offset for the sprite's anchor point.

## Animation: Default

The `<RectAnimation>` tag defines the animation for the sprite.

### Key Attributes

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frame.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frame.
*   **offset\_x**: `4.5` - Horizontal offset for the animation frame.
*   **offset\_y**: `6` - Vertical offset for the animation frame.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `9` - The width of each individual animation frame.
*   **frame\_height**: `11` - The height of each individual animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).