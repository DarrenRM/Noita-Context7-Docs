---
title: Pipe Launcher Sprite
category: items_gfx
---

---

# Pipe Launcher Sprite

This document describes the sprite data for the "Pipe Launcher" item in Noita, used for its visual representation.

## Sprite Attributes

*   **filename**: `data/items_gfx/pipe_launcher.png` - The path to the image file for the sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite's position.
*   **offset\_y**: `3` - Vertical offset for the sprite's position.

## RectAnimation: default

This section defines the animation for the default state of the Pipe Launcher sprite.

### Key Animation Attributes

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `1` - X-coordinate within the sprite sheet for the animation frame.
*   **pos\_y**: `1` - Y-coordinate within the sprite sheet for the animation frame.
*   **offset\_x**: `3` - Horizontal offset specific to this animation frame.
*   **offset\_y**: `4` - Vertical offset specific to this animation frame.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `15` - The width of each individual animation frame.
*   **frame\_height**: `7` - The height of each individual animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).