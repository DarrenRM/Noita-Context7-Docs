---
title: Ghostly Long Torch Stand Sprite
category: props_gfx
---

---

# Ghostly Long Torch Stand Sprite

This document describes the sprite data for the "Ghostly Long Torch Stand" prop in Noita, focusing on its graphical representation and animations.

## Sprite Definition

The primary sprite definition outlines the texture file and its default animation.

### Key Attributes:

*   **filename**: `data/props_gfx/torch_stand_emissive_ghostly_long.png` - The image file containing the sprite frames.
*   **offset_x**: `6` - Horizontal offset for the sprite's origin.
*   **offset_y**: `18` - Vertical offset for the sprite's origin.
*   **default_animation**: `default` - Specifies the animation to play by default.

## Animations

The sprite utilizes `RectAnimation` elements to define different animation sequences.

### `default` Animation

This animation represents the standard visual state of the torch stand.

#### Key Attributes:

*   **name**: `default`
*   **pos_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame_count**: `8` - The total number of frames in this animation.
*   **frame_width**: `12` - The width of each individual frame.
*   **frame_height**: `19` - The height of each individual frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames_per_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.

### `out` Animation

This animation likely represents a state where the torch is extinguished or in a specific "out" phase.

#### Key Attributes:

*   **name**: `out`
*   **pos_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos_y**: `19` - Starting Y position within the sprite sheet for this animation. This indicates it starts on a new row below the `default` animation frames.
*   **frame_count**: `1` - This animation consists of a single frame.
*   **frame_width**: `12` - The width of the frame.
*   **frame_height**: `19` - The height of the frame.
*   **frame_wait**: `0.1` - The duration each frame is displayed.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet for this animation's row.
*   **loop**: `1` - Indicates that the animation should loop.