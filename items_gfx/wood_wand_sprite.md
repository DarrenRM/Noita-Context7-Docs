---
title: Wood Wand Sprite
category: items_gfx
---

---

# Wood Wand Sprite

This document describes the sprite definition for the "wood_01" wand in Noita.

## Sprite Definition

The primary sprite for this wand is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/wands/custom/wood_01.png` - Specifies the image file used for the sprite.

## RectAnimation Definition

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `1` - The starting X position within the sprite sheet.
*   **pos\_y**: `1` - The starting Y position within the sprite sheet.
*   **offset\_x**: `3` - Horizontal offset for the sprite.
*   **offset\_y**: `3` - Vertical offset for the sprite.
*   **has\_offset**: `1` - Indicates that an offset is applied.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `7` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop.