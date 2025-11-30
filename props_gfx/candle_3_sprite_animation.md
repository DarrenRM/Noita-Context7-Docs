---
title: Candle 3 Sprite Animation
category: props_gfx
---

# Candle 3 Sprite Animation

This document details the sprite animation data for `candle_3.xml`, a graphical asset for Noita.

## Sprite Definition

The primary sprite definition outlines the visual asset and its default animation.

### Key Attributes:

*   **filename**: `data/props_gfx/candle_3.png` - The path to the sprite image file.
*   **offset\_x**: `4.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `13` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default when the sprite is active.

## Animations

The `Sprite` element contains definitions for different animation states.

### `stand` Animation

This animation likely represents the candle in its normal, lit state.

#### Key Attributes:

*   **name**: `"stand"`
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet.
*   **frame\_count**: `"4"` - The total number of frames in this animation.
*   **frame\_width**: `"9"` - The width of each individual frame.
*   **frame\_height**: `"14"` - The height of each individual frame.
*   **frame\_wait**: `"0.1"` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `"4"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop continuously.

### `out` Animation

This animation likely represents the candle in an unlit or extinguished state.

#### Key Attributes:

*   **name**: `"out"`
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet.
*   **frame\_count**: `"1"` - The total number of frames in this animation.
*   **frame\_width**: `"9"` - The width of each individual frame.
*   **frame\_height**: `"14"` - The height of each individual frame.
*   **frame\_wait**: `"0.1"` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `"1"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop continuously.