---
title: Telegun Sprite Data
category: items_gfx
---

# Telegun Sprite Data

This document details the sprite information for the "telegun" item in Noita.

## Sprite Definition

The primary sprite for the telegun is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/telegun.png` - The path to the sprite image file.
*   **offset_x**: `6` - Horizontal offset for the sprite.
*   **offset_y**: `3` - Vertical offset for the sprite.

## Animation Data

The telegun utilizes a single animation named "default".

### Animation: `default`

This animation defines how the sprite is rendered and animated.

#### Key Attributes:

*   **name**: `default` - The name of the animation.
*   **pos_x**: `1` - Starting X position within the sprite sheet.
*   **pos_y**: `1` - Starting Y position within the sprite sheet.
*   **offset_x**: `3` - Horizontal offset for the animation frame.
*   **offset_y**: `4` - Vertical offset for the animation frame.
*   **has_offset**: `1` - Indicates that the `offset_x` and `offset_y` attributes are used.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `14` - The width of each individual animation frame.
*   **frame_height**: `6` - The height of each individual animation frame.
*   **frame_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates that the animation does not loop (plays once).