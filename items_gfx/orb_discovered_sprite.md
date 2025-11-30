---
title: Orb Discovered Sprite
category: items_gfx
---

# Orb Discovered Sprite

This document describes the sprite data for the "orb_discovered" item in Noita, focusing on its graphical representation and animation.

## Sprite Definition

The primary sprite for the orb is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/orbs/orb_discovered.png` - Specifies the image file used for the sprite.
*   **offset_x**: `20` - Horizontal offset for the sprite's position.
*   **offset_y**: `48` - Vertical offset for the sprite's position.
*   **default_animation**: `"default"` - Links to the default animation sequence.

## Animation Details

The animation for the orb is defined within the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `"default"` - The name of this animation sequence.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `7` - The total number of frames in the animation.
*   **frame_width**: `40` - The width of each individual frame.
*   **frame_height**: `50` - The height of each individual frame.
*   **frame_wait**: `0.12` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation will loop continuously (1 for true, 0 for false).