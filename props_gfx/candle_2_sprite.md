---
title: Candle 2 Sprite
category: props_gfx
---

# Candle 2 Sprite

This document describes the sprite data for `candle_2.xml`, a graphical asset used for a candle prop in Noita.

## Sprite Definition

The main `<Sprite>` element defines the visual appearance and animation properties.

### Key Attributes:

*   **filename**: `data/props_gfx/candle_2.png` - Specifies the image file containing the sprite frames.
*   **offset_x**: `4.5` - Horizontal offset for the sprite's origin.
*   **offset_y**: `13` - Vertical offset for the sprite's origin.
*   **default_animation**: `stand` - The animation that plays by default when the sprite is active.

## Animations

The sprite includes definitions for different animation states.

### `stand` Animation

This animation represents the candle in its lit or standing state.

#### Key Attributes:

*   **name**: `stand` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet.
*   **pos_y**: `0` - Starting Y position within the sprite sheet.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `9` - The width of each individual frame.
*   **frame_height**: `14` - The height of each individual frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.

### `out` Animation

This animation likely represents the candle when it is extinguished or in an "out" state.

#### Key Attributes:

*   **name**: `out` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet.
*   **pos_y**: `0` - Starting Y position within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `9` - The width of each individual frame.
*   **frame_height**: `14` - The height of each individual frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.