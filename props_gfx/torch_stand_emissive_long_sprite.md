---
title: Torch Stand Emissive Long Sprite
category: props_gfx
---

# Torch Stand Emissive Long Sprite

This document describes the sprite data for the "torch_stand_emissive_long" prop in Noita, focusing on its graphical representation and animations.

## Sprite Definition

The main sprite definition for the torch stand.

### Key Attributes:

*   **filename**: `data/props_gfx/torch_stand_emissive_long.png` - The path to the sprite image file.
*   **offset_x**: `6` - Horizontal offset for the sprite.
*   **offset_y**: `18` - Vertical offset for the sprite.
*   **default_animation**: `default` - Specifies the animation to play by default.

## Animations

This section details the different animations defined for the sprite.

### `default` Animation

This is the primary animation for the torch stand, likely representing its active state.

#### Key Attributes:

*   **name**: `default`
*   **pos_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame_count**: `8` - The total number of frames in this animation.
*   **frame_width**: `12` - The width of each individual frame.
*   **frame_height**: `19` - The height of each individual frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames_per_row**: `8` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

### `out` Animation

This animation likely represents the torch being extinguished or in a deactivated state.

#### Key Attributes:

*   **name**: `out`
*   **pos_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos_y**: `19` - Starting Y position within the sprite sheet for this animation. This suggests the `out` animation frames are located below the `default` animation frames on the sprite sheet.
*   **frame_count**: `1` - This animation consists of a single frame.
*   **frame_width**: `12` - The width of the frame.
*   **frame_height**: `19` - The height of the frame.
*   **frame_wait**: `0.1` - The duration each frame is displayed.
*   **frames_per_row**: `4` - The number of frames arranged horizontally.
*   **loop**: `1` - Indicates that the animation should loop.