---
title: Bomb Wand Sprite
category: items_gfx
---

---

# Bomb Wand Sprite

This documentation describes the sprite definition for the Bomb Wand item in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual representation of the item.

### Key Attributes:

*   **filename**: `data/items_gfx/bomb_wand.png` - Specifies the image file used for the sprite.

## RectAnimation Definition

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `1` - The starting X position within the sprite sheet.
*   **pos\_y**: `1` - The starting Y position within the sprite sheet.
*   **offset\_x**: `3` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `3` - Vertical offset for the sprite's origin.
*   **has\_offset**: `1` - Indicates that an offset is applied.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `13` - The width of each individual frame.
*   **frame\_height**: `7` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop.