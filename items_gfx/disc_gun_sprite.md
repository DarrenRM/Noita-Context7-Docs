---
title: Disc Gun Sprite
category: items_gfx
---

# Disc Gun Sprite

This documentation describes the sprite definition for the Disc Gun item in Noita.

## Sprite Definition

The primary sprite for the Disc Gun is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/disc_gun.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite's position.
*   **offset\_y**: `3` - Vertical offset for the sprite's position.

## Animation Definition

The Disc Gun utilizes a single animation state named "default".

### Key Attributes:

*   **name**: `default` - The name of the animation state.
*   **pos\_x**: `1` - Starting X position within the sprite sheet for the animation frame.
*   **pos\_y**: `1` - Starting Y position within the sprite sheet for the animation frame.
*   **offset\_x**: `3` - Additional horizontal offset specific to this animation frame.
*   **offset\_y**: `4` - Additional vertical offset specific to this animation frame.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual animation frame.
*   **frame\_height**: `6` - The height of each individual animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).