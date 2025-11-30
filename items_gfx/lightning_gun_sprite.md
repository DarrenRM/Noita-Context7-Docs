---
title: Lightning Gun Sprite
category: items_gfx
---

# Lightning Gun Sprite

This documentation describes the sprite and animation data for the Lightning Gun item in Noita.

## Sprite Data

The primary sprite for the Lightning Gun is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/lightninggun.png` - The path to the image file containing the sprite.
*   **offset_x**: `6` - Horizontal offset for the sprite's position.
*   **offset_y**: `3` - Vertical offset for the sprite's position.

## Animation Data

The `<RectAnimation>` tag defines the animation for the Lightning Gun.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos_x**: `1` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **offset_x**: `3` - Horizontal offset specific to this animation frame.
*   **offset_y**: `4` - Vertical offset specific to this animation frame.
*   **has_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are used.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `17` - The width of each individual frame.
*   **frame_height**: `9` - The height of each individual frame.
*   **frame_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays only once).