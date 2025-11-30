---
title: Egg Sprite Animation
category: data/buildings_gfx
---

---

# Egg Sprite Animation

This document describes the sprite animations for the "egg" building in Noita, focusing on its visual representation and animation states.

## Sprite Definition

The primary sprite definition for the egg is as follows:

*   **filename**: `data/buildings_gfx/egg.png` - The image file containing the egg's graphical assets.
*   **offset_x**: `24` - Horizontal offset for the sprite.
*   **offset_y**: `64` - Vertical offset for the sprite.
*   **default_animation**: `stand` - The animation state that plays by default when the egg is idle.

## Animations

The egg has two defined animation states: `stand` and `open`.

### `stand` Animation

This animation represents the egg in its resting or idle state.

*   **name**: `stand`
*   **pos_x**: `0` - Starting X position within the sprite sheet.
*   **pos_y**: `0` - Starting Y position within the sprite sheet.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `48` - The width of each individual frame.
*   **frame_height**: `72` - The height of each individual frame.
*   **frame_wait**: `0.3` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `6` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that this animation should loop continuously.

### `open` Animation

This animation represents the egg hatching or opening.

*   **name**: `open`
*   **pos_x**: `0` - Starting X position within the sprite sheet.
*   **pos_y**: `72` - Starting Y position within the sprite sheet. This indicates the `open` animation starts below the `stand` animation frames in the sprite sheet.
*   **frame_count**: `6` - The total number of frames in this animation.
*   **frame_width**: `48` - The width of each individual frame.
*   **frame_height**: `72` - The height of each individual frame.
*   **frame_wait**: `0.09` - The duration (in seconds) each frame is displayed. This is a faster animation than `stand`.
*   **frames_per_row**: `6` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `0` - Indicates that this animation should play only once and not loop.