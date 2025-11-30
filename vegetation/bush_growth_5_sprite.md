---
title: Bush Growth 5 Sprite
category: data/vegetation
---

---

# Bush Growth 5 Sprite

This document describes the sprite and animation data for `bush_growth_5.xml`, used for a growing bush entity in Noita.

## Sprite Definition

The primary sprite definition for this growing bush.

### Key Attributes:

*   **filename**: `data/vegetation/bush_growth_5.png` - The image file containing the sprite frames.
*   **offset_x**: `18` - Horizontal offset for the sprite's origin.
*   **offset_y**: `31` - Vertical offset for the sprite's origin.
*   **default_animation**: `vegetation_growth` - Specifies the default animation to play.

## Animation Definition: `vegetation_growth`

This is a special animation name in Noita that signifies a growing vegetation entity.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos_y**: `0` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **frame_count**: `6` - The total number of frames in the animation.
*   **frame_width**: `32` - The width of each individual frame.
*   **frame_height**: `34` - The height of each individual frame.
*   **frame_wait**: `1.0` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).