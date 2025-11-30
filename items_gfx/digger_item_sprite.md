---
title: Digger Item Sprite
category: items_gfx
---

```

# Digger Item Sprite

This documentation describes the sprite and animation data for the "digger" item in Noita.

## Sprite Definition

The `Sprite` element defines the visual representation of the item.

### Key Attributes:

*   **`filename`**: `data/items_gfx/digger.png` - Specifies the image file used for the sprite.
*   **`offset_x`**: `3` - Horizontal offset for the sprite's position.
*   **`offset_y`**: `4` - Vertical offset for the sprite's position.

## Animation Definition

The `RectAnimation` element defines how the sprite is animated.

### Key Attributes:

*   **`name`**: `default` - The name of this animation state.
*   **`pos_x`**: `1` - Starting X position within the sprite sheet.
*   **`pos_y`**: `1` - Starting Y position within the sprite sheet.
*   **`offset_x`**: `3` - Horizontal offset for the animation.
*   **`offset_y`**: `4` - Vertical offset for the animation.
*   **`has_offset`**: `1` - Indicates that offsets are applied.
*   **`frame_count`**: `1` - The total number of frames in the animation.
*   **`frame_width`**: `12` - The width of each individual frame.
*   **`frame_height`**: `6` - The height of each individual frame.
*   **`frame_wait`**: `0.2` - The duration (in seconds) each frame is displayed.
*   **`frames_per_row`**: `10` - The number of frames that fit horizontally in the sprite sheet.
*   **`loop`**: `0` - Indicates that the animation does not loop.