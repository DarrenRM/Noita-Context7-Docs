---
title: Blue Torch Stand Sprite
category: props_gfx
---

# Blue Torch Stand Sprite

This document describes the sprite data for the blue torch stand prop in Noita.

## Sprite Definition

The main `Sprite` element defines the base image and its default animation.

### Key Attributes:

*   **filename**: `data/props_gfx/torch_stand_blue.png` - The path to the sprite image file.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `18` - Vertical offset for the sprite.
*   **default\_animation**: `"default"` - Specifies the animation to play by default.

## Animations

The sprite uses `RectAnimation` elements to define different animation sequences.

### `default` Animation

This animation represents the active, lit state of the torch stand.

#### Key Attributes:

*   **name**: `"default"`
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `8` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `19` - The height of each individual frame.
*   **frame\_wait**: `0.08` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop.

### `out` Animation

This animation likely represents the torch stand when it is unlit or extinguished.

#### Key Attributes:

*   **name**: `"out"`
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `"19"` - Starting Y position within the sprite sheet for this animation. This indicates it's on a different row than the `default` animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `19` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop.