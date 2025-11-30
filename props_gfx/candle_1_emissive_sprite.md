---
title: Candle 1 Emissive Sprite
category: props_gfx
---

# Candle 1 Emissive Sprite

This document describes the sprite data for the "candle_1_emissive" prop in Noita, focusing on its graphical representation and animations.

## Sprite Definition

The primary sprite definition for the candle is as follows:

*   **filename**: `data/props_gfx/candle_1_emissive.png` - The image file containing the sprite frames.
*   **offset\_x**: `4.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `13` - Vertical offset for the sprite's origin.
*   **default\_animation**: `default` - Specifies the animation to play by default.

## Animations

The sprite includes two distinct animations:

### `default` Animation

This animation represents the standard, lit state of the candle.

*   **name**: `default`
*   **pos\_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `4` - The total number of frames in this animation.
*   **frame\_width**: `9` - The width of each individual frame.
*   **frame\_height**: `14` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.

### `out` Animation

This animation likely represents the candle being extinguished or in an "off" state.

*   **name**: `out`
*   **pos\_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `14` - Starting Y position within the sprite sheet for this animation. This suggests the "out" frames are located below the "default" frames in the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `9` - The width of each individual frame.
*   **frame\_height**: `14` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.