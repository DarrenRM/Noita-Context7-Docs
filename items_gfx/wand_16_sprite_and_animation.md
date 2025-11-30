---
title: Wand 16 Sprite and Animation
category: items_gfx
---

---

# Wand 16 Sprite and Animation

This document describes the graphical assets for "Wand 16" in Noita, focusing on its sprite and animation data.

## Sprite

The primary sprite for Wand 16 is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/wand_16.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `6` - Horizontal offset of the sprite from its origin.
*   **offset\_y**: `3` - Vertical offset of the sprite from its origin.

## RectAnimation

The animation for Wand 16 is handled by the `<RectAnimation>` tag, named "default".

### Key Attributes:

*   **name**: `default` - The identifier for this animation.
*   **pos\_x**: `1` - Starting X position within the sprite sheet for the animation frame.
*   **pos\_y**: `1` - Starting Y position within the sprite sheet for the animation frame.
*   **offset\_x**: `3` - Horizontal offset applied to the animated frame.
*   **offset\_y**: `4` - Vertical offset applied to the animated frame.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `15` - The width of each individual animation frame.
*   **frame\_height**: `7` - The height of each individual animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Specifies that the animation does not loop (plays only once).