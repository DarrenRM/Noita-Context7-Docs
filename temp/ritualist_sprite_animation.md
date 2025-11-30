---
title: Ritualist Sprite Animation
category: data/temp
---

---

# Ritualist Sprite Animation

This document describes the sprite and animation data for the "ritualist_d" entity in Noita.

## Sprite Definition

The primary sprite for the ritualist is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/temp/ritualist_d.png` - The path to the sprite image file.
*   **offset_x**: `10` - Horizontal offset of the sprite.
*   **offset_y**: `21` - Vertical offset of the sprite.
*   **default_animation**: `dance` - The animation to play by default.

## Animation: `dance`

The `dance` animation is a rectangular animation sequence.

### Key Attributes:

*   **name**: `dance` - The name of this animation.
*   **pos_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame_count**: `8` - The total number of frames in the animation.
*   **frame_width**: `20` - The width of each individual frame.
*   **frame_height**: `22` - The height of each individual frame.
*   **frame_wait**: `0.1206` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).