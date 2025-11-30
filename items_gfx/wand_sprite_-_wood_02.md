---
title: Wand Sprite - Wood 02
category: data/items_gfx/
---

# Wand Sprite - Wood 02

This documentation describes the sprite definition for a custom wand in Noita, specifically `wood_02`.

## Sprite Definition

The core of this definition is the `<Sprite>` tag, which points to the image file used for the wand's visual representation.

### Key Attributes:

*   **`filename`**: `data/items_gfx/wands/custom/wood_02.png` - The path to the sprite image file.

## RectAnimation Definition

This section defines how the sprite is animated. For `wood_02`, it's a static sprite with a single frame.

### Key Attributes:

*   **`name`**: `default` - The name of this animation state.
*   **`pos_x`, `pos_y`**: `1`, `1` - The starting X and Y coordinates within the sprite sheet for the animation.
*   **`offset_x`, `offset_y`**: `3`, `3` - The offset applied to the sprite's position.
*   **`has_offset`**: `1` - Indicates that an offset is applied.
*   **`frame_count`**: `1` - The total number of frames in the animation.
*   **`frame_width`, `frame_height`**: `17`, `7` - The dimensions of each individual frame.
*   **`frame_wait`**: `0.2` - The time in seconds to wait between frames (though with `frame_count="1"`, this is less relevant).
*   **`frames_per_row`**: `10` - The number of frames that fit horizontally in the sprite sheet.
*   **`loop`**: `0` - Indicates that the animation does not loop.