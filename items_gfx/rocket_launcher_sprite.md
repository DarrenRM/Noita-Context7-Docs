---
title: Rocket Launcher Sprite
category: items_gfx
---

---

# Rocket Launcher Sprite

This document describes the sprite and animation data for the Rocket Launcher item in Noita.

## Sprite

The main sprite for the Rocket Launcher.

### Key Attributes:

*   **filename**: `data/items_gfx/rocketlauncher.png` - The path to the sprite image file.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `3` - Vertical offset for the sprite.

## RectAnimation: default

Defines the default animation for the Rocket Launcher sprite.

### Key Attributes:

*   **name**: `default` - The name of this animation.
*   **pos\_x**: `1` - Starting X position within the sprite sheet.
*   **pos\_y**: `1` - Starting Y position within the sprite sheet.
*   **offset\_x**: `3` - Animation-specific horizontal offset.
*   **offset\_y**: `4` - Animation-specific vertical offset.
*   **has\_offset**: `1` - Indicates that an offset is applied.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `18` - The width of each individual frame.
*   **frame\_height**: `7` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Whether the animation should loop (0 for no, 1 for yes).