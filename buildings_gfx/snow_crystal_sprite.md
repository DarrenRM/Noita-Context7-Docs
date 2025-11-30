---
title: Snow Crystal Sprite
category: data/buildings_gfx
---

# Snow Crystal Sprite

This document describes the sprite definition for the Snow Crystal in Noita, focusing on its visual representation and animation.

## Sprite Definition

The primary sprite definition for the Snow Crystal is provided by the `<Sprite>` tag.

### Key Attributes

*   **filename**: `data/buildings_gfx/snowcrystal.png` - Specifies the image file used for the sprite.
*   **offset_x**: `13` - The horizontal offset of the sprite's origin.
*   **offset_y**: `23` - The vertical offset of the sprite's origin.
*   **default_animation**: `stand` - The name of the animation that plays by default.

## Animation: `stand`

The `stand` animation defines how the Snow Crystal visually behaves.

### Key Attributes

*   **name**: `stand` - The identifier for this animation.
*   **pos_x**: `0` - The starting X position within the sprite sheet for this animation.
*   **pos_y**: `0` - The starting Y position within the sprite sheet for this animation.
*   **frame_count**: `18` - The total number of frames in this animation.
*   **frame_width**: `26` - The width of each individual frame.
*   **frame_height**: `26` - The height of each individual frame.
*   **frame_wait**: `0.15` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `18` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).