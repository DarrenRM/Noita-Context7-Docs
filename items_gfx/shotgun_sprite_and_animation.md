---
title: Shotgun Sprite and Animation
category: items_gfx
---

# Shotgun Sprite and Animation

This document describes the graphical assets for the "shotgun" item in Noita, focusing on its sprite and animation data.

## Sprite

The main visual representation of the shotgun is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/shotgun.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite's position.
*   **offset\_y**: `3` - Vertical offset for the sprite's position.

## Animation

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `1` - Starting X position within the sprite sheet for the animation frame.
*   **pos\_y**: `1` - Starting Y position within the sprite sheet for the animation frame.
*   **offset\_x**: `3` - Horizontal offset specific to this animation frame.
*   **offset\_y**: `4` - Vertical offset specific to this animation frame.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `15` - The width of each individual animation frame.
*   **frame\_height**: `7` - The height of each individual animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `10` - The number of frames that fit horizontally in a single row of the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).