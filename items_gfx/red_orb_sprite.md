---
title: Red Orb Sprite
category: items_gfx
---

---

# Red Orb Sprite

This documentation describes the sprite definition for the Red Orb item in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual representation of the Red Orb.

### Key Attributes:

*   **filename**: `data/items_gfx/orbs/orb_red.png` - Specifies the texture file used for the sprite.
*   **offset_x**: `20` - Horizontal offset for the sprite's position.
*   **offset_y**: `48` - Vertical offset for the sprite's position.
*   **default_animation**: `default` - Sets the initial animation to play.

## Animation Definition

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `default` - The name of this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `7` - The total number of frames in the animation.
*   **frame_width**: `40` - The width of each individual frame.
*   **frame_height**: `50` - The height of each individual frame.
*   **frame_wait**: `0.12` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames_per_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).