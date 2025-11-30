---
title: Rifle Sprite and Animation
category: items_gfx
---

# Rifle Sprite and Animation

This documentation describes the sprite and animation data for the "rifle" item in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite for the rifle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/items_gfx/rifle.png` - Specifies the image file used for the sprite.
*   **`offset_x`**: `6` - Horizontal offset for the sprite's position.
*   **`offset_y`**: `3` - Vertical offset for the sprite's position.

## Animation Definition

The `<RectAnimation>` tag defines the animation sequence for the rifle.

### Key Attributes:

*   **`name`**: `default` - The name of this animation state.
*   **`pos_x`**: `1` - Starting X position within the sprite sheet for the animation frame.
*   **`pos_y`**: `1` - Starting Y position within the sprite sheet for the animation frame.
*   **`offset_x`**: `3` - Horizontal offset specific to this animation frame.
*   **`offset_y`**: `4` - Vertical offset specific to this animation frame.
*   **`has_offset`**: `1` - Indicates that the `offset_x` and `offset_y` attributes are used.
*   **`frame_count`**: `1` - The total number of frames in this animation.
*   **`frame_width`**: `12` - The width of each individual animation frame.
*   **`frame_height`**: `6` - The height of each individual animation frame.
*   **`frame_wait`**: `0.2` - The duration (in seconds) each frame is displayed.
*   **`frames_per_row`**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays once).