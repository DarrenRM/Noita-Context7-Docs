---
title: Grass Patch 05 Sprite
category: data
---

# Grass Patch 05 Sprite

This document describes the sprite and animation data for `grass_patch_05.xml`, a vegetation asset in Noita.

## Sprite

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/grass_patch_05.png` - Specifies the image file used for the sprite.
*   **offset_x**: `10` - Horizontal offset of the sprite's origin.
*   **offset_y**: `9` - Vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The name of the animation to play by default. This is a special name that triggers a growing vegetation effect.

## Animation

The `vegetation_growth` animation is a special type that creates a growing vegetation effect.

### Key Attributes for `vegetation_growth`:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `20` - The width of each individual frame.
*   **frame_height**: `10` - The height of each individual frame.
*   **frame_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).