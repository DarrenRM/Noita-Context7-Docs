---
title: Nuke Launcher Sprite
category: items_gfx
---

---

# Nuke Launcher Sprite

This documentation describes the sprite and animation data for the Nuke Launcher item in Noita.

## Sprite

The main sprite for the Nuke Launcher.

### Key Attributes:

*   **filename**: `data/items_gfx/nukelauncher.png` - The path to the sprite image file.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `3` - Vertical offset for the sprite.

## RectAnimation: default

Defines the animation for the default state of the Nuke Launcher.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `1` - X position within the sprite sheet for the animation frame.
*   **pos\_y**: `1` - Y position within the sprite sheet for the animation frame.
*   **offset\_x**: `3` - Horizontal offset for the animation frame.
*   **offset\_y**: `4` - Vertical offset for the animation frame.
*   **has\_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are used.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `18` - The width of each animation frame.
*   **frame\_height**: `7` - The height of each animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop.