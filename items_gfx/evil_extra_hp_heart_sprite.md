---
title: Evil Extra HP Heart Sprite
category: items_gfx
---

---

# Evil Extra HP Heart Sprite

This document describes the sprite data for the "Evil Extra HP Heart" item in Noita, used for visual representation.

## Sprite Definition

The primary sprite definition is enclosed within the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/heart_extrahp_evil.png` - Specifies the image file used for the sprite.
*   **offset_x**: `8` - Horizontal offset for the sprite's position.
*   **offset_y**: `21` - Vertical offset for the sprite's position.
*   **default_animation**: `default` - Links to the default animation sequence.

## Animation Definition

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `default` - The name of this animation sequence.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `4` - The total number of frames in the animation.
*   **frame_width**: `20` - The width of each individual frame.
*   **frame_height**: `20` - The height of each individual frame.
*   **frame_wait**: `0.12` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).