---
title: Kantele Sprite
category: items_gfx
---

# Kantele Sprite

This documentation describes the sprite definition for the Kantele item in Noita.

## Sprite Definition

The `Sprite` element defines the visual representation of the Kantele.

### Key Attributes

*   **filename**: `data/items_gfx/kantele.png` - Specifies the path to the sprite image file.

## RectAnimation

The `RectAnimation` element defines the animation for the sprite.

### Key Attributes

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `1` - The starting X position within the sprite sheet.
*   **pos\_y**: `1` - The starting Y position within the sprite sheet.
*   **offset\_x**: `1` - Horizontal offset for the sprite.
*   **offset\_y**: `3.5` - Vertical offset for the sprite.
*   **has\_offset**: `1` - Indicates that an offset is applied.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `14` - The width of each individual frame.
*   **frame\_height**: `7` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop.