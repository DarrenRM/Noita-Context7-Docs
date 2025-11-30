---
title: Orb 01 Sprite Definition
category: items_gfx
---

---

# Orb 01 Sprite Definition

This document details the sprite definition for "orb_01" in Noita, focusing on its visual representation and animation.

## Sprite Attributes

The `<Sprite>` tag defines the primary visual asset for the orb.

### Key Attributes:

*   **filename**: `data/items_gfx/orbs/orb_01.png` - Specifies the image file used for the sprite.
*   **offset_x**: `20` - Horizontal offset for the sprite's position.
*   **offset_y**: `48` - Vertical offset for the sprite's position.
*   **default_animation**: `default` - Links to the default animation sequence defined within this sprite.

## Animation Definition

The `<RectAnimation>` tag describes how the sprite animates.

### Key Attributes:

*   **name**: `default` - The name of this animation sequence.
*   **pos_x**: `0` - X-coordinate within the sprite sheet for the animation's starting frame.
*   **pos_y**: `0` - Y-coordinate within the sprite sheet for the animation's starting frame.
*   **frame_count**: `7` - The total number of frames in this animation.
*   **frame_width**: `40` - The width of each individual frame.
*   **frame_height**: `50` - The height of each individual frame.
*   **frame_wait**: `0.12` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).