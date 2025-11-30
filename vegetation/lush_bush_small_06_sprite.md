---
title: Lush Bush Small 06 Sprite
category: data
---

# Lush Bush Small 06 Sprite

This document describes the sprite data for the `lush_bush_small_06` vegetation entity in Noita.

## Sprite Definition

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/lush_bush_small_06.png` - Specifies the image file used for the sprite.
*   **offset_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset_y**: `30` - The vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The default animation to play when the entity is spawned. This is a special animation name that triggers vegetation growth.

## Animation: vegetation_growth

The `vegetation_growth` animation is a special type of animation in Noita that handles the visual progression of vegetation.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos_x**: `0` - The X position of the animation's starting frame within the sprite sheet.
*   **pos_y**: `0` - The Y position of the animation's starting frame within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `32` - The width of each individual frame.
*   **frame_height**: `32` - The height of each individual frame.
*   **frame_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).