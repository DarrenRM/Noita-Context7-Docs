---
title: Cement Thrower Sprite
category: items_gfx
---

# Cement Thrower Sprite

This documentation describes the sprite and animation data for the "cement_thrower" item in Noita.

## Sprite Data

The primary sprite for the cement thrower is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/cement_thrower.png` - The path to the image file used for the sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite's position.
*   **offset\_y**: `3` - Vertical offset for the sprite's position.

## Animation Data

The cement thrower has a single animation defined, named "default".

### Key Attributes:

*   **name**: `default` - The name of the animation.
*   **pos\_x**: `1` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `1` - Starting Y position within the sprite sheet for the animation frames.
*   **offset\_x**: `3` - Horizontal offset applied during the animation.
*   **offset\_y**: `4` - Vertical offset applied during the animation.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual animation frame.
*   **frame\_height**: `6` - The height of each individual animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).