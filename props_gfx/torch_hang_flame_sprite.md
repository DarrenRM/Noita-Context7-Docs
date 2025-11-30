---
title: Torch Hang Flame Sprite
category: props_gfx
---

# Torch Hang Flame Sprite

This document describes the sprite data for the hanging torch flame in Noita. It defines the visual appearance and animation of the flame.

## Sprite Definition

The main `<Sprite>` tag defines the texture file and its default animation.

### Key Attributes:

*   **filename**: `data/props_gfx/torch_hang_flame.png` - The path to the image file containing the sprite frames.
*   **offset\_x**: `6` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `18` - Vertical offset for the sprite's origin.
*   **default\_animation**: `default` - Specifies the animation to play by default.

## Animations

The sprite uses `<RectAnimation>` tags to define different animation sequences.

### `default` Animation

This is the primary animation for the torch flame.

*   **name**: `default`
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `8` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `19` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop continuously.

### `out` Animation

This animation appears to be a single frame, possibly for a "dying" or "extinguished" state of the flame.

*   **name**: `out`
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `19` - Starting Y position of the animation frames within the sprite sheet. This suggests the `out` animation frames are located below the `default` animation frames in the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `19` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop continuously.