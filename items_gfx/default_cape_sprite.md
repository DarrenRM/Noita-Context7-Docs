---
title: Default Cape Sprite
category: items_gfx
---

# Default Cape Sprite

This document describes the sprite definition for the default cape item in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual representation of the cape.

### Key Attributes:

*   **filename**: `data/items_gfx/cape/default.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset of the sprite from its origin.
*   **offset\_y**: `12` - Vertical offset of the sprite from its origin.
*   **default\_animation**: `default` - The name of the default animation to play.

## Animation Definition

The `<RectAnimation>` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `default` - The name of this animation.
*   **pos\_x**: `0` - The starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.12` - The time in seconds to wait between frames.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).