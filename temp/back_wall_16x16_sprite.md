---
title: Back Wall 16x16 Sprite
category: data
---

---

# Back Wall 16x16 Sprite

This document describes the sprite definition for a 16x16 back wall tile in Noita.

## Sprite Definition

The core of this definition is the `<Sprite>` tag, which specifies the visual asset and its positioning.

### Key Attributes:

*   **filename**: `data/temp/building/back_wall16.png` - The path to the image file used for this sprite.
*   **offset_x**: `8` - Horizontal offset for the sprite's anchor point.
*   **offset_y**: `8` - Vertical offset for the sprite's anchor point.

## Animation Definition

The `<RectAnimation>` tag defines how the sprite is animated. For this back wall, it's a static image.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **pos_x**: `0` - Starting X position within the sprite sheet.
*   **pos_y**: `0` - Starting Y position within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `16` - The width of a single frame in pixels.
*   **frame_height**: `16` - The height of a single frame in pixels.
*   **frame_wait**: `0.12` - The time in seconds to wait between frames (effectively the animation speed).
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).