---
title: Fire Protection Cape Sprite
category: items_gfx
---

# Fire Protection Cape Sprite

This document describes the sprite data for the Fire Protection Cape in Noita.

## Sprite Data

The primary sprite for the Fire Protection Cape is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/cape/protection_fire.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset of the sprite.
*   **offset\_y**: `12` - Vertical offset of the sprite.
*   **default\_animation**: `default` - The name of the default animation to use.

## Animation Data

The sprite utilizes a single animation named "default".

### Key Attributes:

*   **name**: `default` - The name of this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).