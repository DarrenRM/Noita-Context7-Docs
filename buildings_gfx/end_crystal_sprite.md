---
title: End Crystal Sprite
category: data/buildings_gfx
---

---

# End Crystal Sprite

This documentation describes the sprite definition for the End Crystal in Noita, focusing on its visual representation and animation.

## Sprite Definition

The primary sprite for the End Crystal is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/buildings_gfx/endcrystal.png` - Specifies the image file containing the sprite's assets.
*   **offset_x**: `20` - Horizontal offset for the sprite's position.
*   **offset_y**: `20` - Vertical offset for the sprite's position.
*   **default_animation**: `default` - Sets the initial animation to play.

## Animation Definition

The End Crystal features a default animation named "default".

### Key Attributes of `RectAnimation`:

*   **name**: `default` - The name of this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame_count**: `6` - The total number of frames in this animation.
*   **frame_width**: `40` - The width of each individual animation frame.
*   **frame_height**: `40` - The height of each individual animation frame.
*   **frame_wait**: `0.12` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).