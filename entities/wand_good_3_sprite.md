---
title: Wand Good 3 Sprite
category: entities
---

# Wand Good 3 Sprite

This document describes the sprite and animation data for the "wand_good_3" item in Noita.

## Sprite

The primary sprite for this wand is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/items/wands/wand_good/wand_good_3.png` - Specifies the image file used for the sprite.

## RectAnimation

The `<RectAnimation>` tag defines the animation for the sprite.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `1` - The starting X position within the sprite sheet.
*   **pos\_y**: `1` - The starting Y position within the sprite sheet.
*   **offset\_x**: `3` - Horizontal offset for the sprite.
*   **offset\_y**: `3` - Vertical offset for the sprite.
*   **has\_offset**: `1` - Indicates that an offset is applied.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `14` - The width of each animation frame.
*   **frame\_height**: `7` - The height of each animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames that fit horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop.