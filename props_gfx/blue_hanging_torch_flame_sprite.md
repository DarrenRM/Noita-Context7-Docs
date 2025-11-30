---
title: Blue Hanging Torch Flame Sprite
category: props_gfx
---

# Blue Hanging Torch Flame Sprite

This document describes the sprite data for the blue hanging torch flame in Noita, useful for AI-assisted modding of graphical assets.

## Sprite Definition

The primary sprite definition outlines the texture file and its default animation.

### Key Attributes:

*   **filename**: `data/props_gfx/torch_hang_flame_blue.png` - The path to the sprite's texture file.
*   **offset\_x**: `6` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `18` - Vertical offset for the sprite's origin.
*   **default\_animation**: `default` - Specifies the animation to play by default.

## Animations

The sprite includes two distinct animations: `default` for the active flame and `out` for a potential extinguished state.

### `default` Animation

This animation represents the active, flickering blue flame.

#### Key Attributes:

*   **name**: `default`
*   **pos\_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `8` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `19` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.

### `out` Animation

This animation appears to be a single frame, potentially for an extinguished or inactive state of the torch flame.

#### Key Attributes:

*   **name**: `out`
*   **pos\_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `19` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `19` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.