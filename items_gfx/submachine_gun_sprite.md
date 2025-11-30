---
title: Submachine Gun Sprite
category: items_gfx
---

---

# Submachine Gun Sprite

This documentation describes the sprite data for the Submachine Gun item in Noita.

## Sprite

The main sprite definition for the Submachine Gun.

### Key Attributes:

*   **filename**: `data/items_gfx/submachinegun.png` - The path to the sprite image file.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `3` - Vertical offset for the sprite.

## RectAnimation

Defines the animation for the sprite.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `1` - Starting X position within the sprite sheet for animation frames.
*   **pos\_y**: `1` - Starting Y position within the sprite sheet for animation frames.
*   **offset\_x**: `3` - Horizontal offset specific to this animation.
*   **offset\_y**: `4` - Vertical offset specific to this animation.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are used.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `13` - The width of each individual animation frame.
*   **frame\_height**: `7` - The height of each individual animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays once).