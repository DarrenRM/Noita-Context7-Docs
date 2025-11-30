---
title: Charge Gun Sprite
category: items_gfx
---

# Charge Gun Sprite

This documentation describes the sprite and animation data for the "Charge Gun" item in Noita.

## Sprite Data

The primary sprite for the Charge Gun is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/chargegun.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite's position.
*   **offset\_y**: `3` - Vertical offset for the sprite's position.

## Animation Data

The Charge Gun utilizes a single animation named "default".

### Key Attributes of `RectAnimation` (name="default"):

*   **pos\_x**: `1` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **offset\_x**: `3` - Horizontal offset specific to this animation frame.
*   **offset\_y**: `4` - Vertical offset specific to this animation frame.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `15` - The width of each individual frame.
*   **frame\_height**: `9` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).