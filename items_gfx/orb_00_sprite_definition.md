---
title: Orb 00 Sprite Definition
category: items_gfx
---

---

# Orb 00 Sprite Definition

This document describes the sprite definition for the "Orb 00" item in Noita, focusing on its visual representation and animation.

## Sprite Attributes

The `<Sprite>` tag defines the primary visual asset for the orb.

### Key Attributes:

*   **filename**: `data/items_gfx/orbs/orb_00.png` - Specifies the image file used for the sprite.
*   **offset_x**: `20` - Horizontal offset for the sprite's position.
*   **offset_y**: `48` - Vertical offset for the sprite's position.
*   **default_animation**: `default` - Links to the default animation sequence defined within this sprite.

## Animation Definition

The `<RectAnimation>` tag defines how the sprite animates.

### Key Attributes:

*   **name**: `default` - The name of this animation sequence.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `7` - The total number of frames in the animation.
*   **frame_width**: `40` - The width of each individual frame.
*   **frame_height**: `50` - The height of each individual frame.
*   **frame_wait**: `0.12` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).