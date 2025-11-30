---
title: Candle 2 Emissive Sprite
category: props_gfx
---

---

# Candle 2 Emissive Sprite

This document describes the sprite data for `candle_2_emissive.xml`, used for a candle prop with emissive properties in Noita.

## Sprite Definition

The main `<Sprite>` element defines the texture file and default animation.

### Key Attributes:

*   **filename**: `data/props_gfx/candle_2_emissive.png` - The texture file containing the sprite frames.
*   **offset_x**: `4.5` - Horizontal offset for the sprite's origin.
*   **offset_y**: `13` - Vertical offset for the sprite's origin.
*   **default_animation**: `default` - Specifies the animation to play by default.

## Animations

The sprite utilizes two distinct animations: `default` and `out`.

### `default` Animation

This animation likely represents the active, lit state of the candle.

#### Key Attributes:

*   **name**: `default`
*   **pos_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `9` - The width of each individual frame.
*   **frame_height**: `14` - The height of each individual frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `4` - How many frames are arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop.

### `out` Animation

This animation likely represents the candle being extinguished or in an inactive state.

#### Key Attributes:

*   **name**: `out`
*   **pos_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos_y**: `14` - Starting Y position within the sprite sheet for this animation. This suggests the `out` animation frames are located below the `default` animation frames on the sprite sheet.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `9` - The width of each individual frame.
*   **frame_height**: `14` - The height of each individual frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `1` - How many frames are arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop.