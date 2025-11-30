---
title: Erect Wand Sprite
category: items_gfx
---

---

# Erect Wand Sprite

This documentation describes the sprite definition for the "Erect Wand" item in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual representation of the item.

### Key Attributes:

*   **filename**: `data/items_gfx/erect_wand.png` - The path to the image file used for the sprite.
*   **offset\_x**: `3` - Horizontal offset for the sprite's position.
*   **offset\_y**: `10` - Vertical offset for the sprite's position.

## RectAnimation

The `<RectAnimation>` element defines how the sprite animates.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `0` - The starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - The starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `7` - The width of each individual frame.
*   **frame\_height**: `15` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The time in seconds to wait between frames.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).