---
title: Wand Sprite - Good 01
category: items_gfx
---

```

# Wand Sprite - Good 01

This document describes the sprite definition for the "good_01" wand in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual representation of the wand.

### Key Attributes:

*   **filename**: `data/items_gfx/wands/custom/good_01.png` - Specifies the image file used for the sprite.

## RectAnimation Definition

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos\_x**: `1` - The starting X position within the sprite sheet.
*   **pos\_y**: `1` - The starting Y position within the sprite sheet.
*   **offset\_x**: `3` - The horizontal offset of the sprite.
*   **offset\_y**: `4` - The vertical offset of the sprite.
*   **frame\_width**: `23` - The width of a single animation frame.
*   **frame\_height**: `9` - The height of a single animation frame.
*   **has\_offset**: `1` - Indicates that the sprite has an offset.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop.