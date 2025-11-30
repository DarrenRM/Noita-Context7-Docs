---
title: Wand Sprite - Good 02
category: items_gfx
---

---

# Wand Sprite - Good 02

This document describes the sprite definition for the "good_02" wand in Noita.

## Sprite Definition

The primary sprite for this wand is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/wands/custom/good_02.png` - Specifies the image file used for the sprite.

## RectAnimation Definition

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos_x**: `1` - The starting X position within the sprite sheet.
*   **pos_y**: `1` - The starting Y position within the sprite sheet.
*   **offset_x**: `3` - The horizontal offset of the sprite.
*   **offset_y**: `4` - The vertical offset of the sprite.
*   **frame_width**: `23` - The width of a single animation frame.
*   **frame_height**: `9` - The height of a single animation frame.
*   **has_offset**: `1` - Indicates that the sprite has an offset.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop.