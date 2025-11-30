---
title: Bush Growth 3 Sprite and Animation
category: data
---

---

# Bush Growth 3 Sprite and Animation

This document describes the sprite and animation data for `bush_growth_3.xml`, a vegetation asset in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual appearance and animation for the bush.

### Key Attributes:

*   **filename**: `data/vegetation/bush_growth_3.png` - Specifies the image file used for the sprite.
*   **offset_x**: `18` - Horizontal offset of the sprite's origin.
*   **offset_y**: `31` - Vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The name of the animation to play by default. This is a special name that triggers vegetation growth.

## Animation Definition

The `<RectAnimation>` element defines the frames and timing for the `vegetation_growth` animation.

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