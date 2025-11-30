---
title: Torch Stand Sprite Animation
category: props_gfx
---

# Torch Stand Sprite Animation

This document describes the sprite animations for the `torch_stand.xml` file, used for the torch stand prop in Noita.

## Sprite Definition

The main `Sprite` element defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/props_gfx/torch_stand.png` - The path to the sprite sheet.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `18` - Vertical offset for the sprite.
*   **default\_animation**: `default` - Specifies the animation to play by default.

## Animations

The file defines two distinct animations: `default` and `out`.

### `default` Animation

This animation likely represents the active, burning state of the torch stand.

#### Key Attributes:

*   **name**: `default`
*   **pos\_x**: `0` - Starting X position on the sprite sheet.
*   **pos\_y**: `0` - Starting Y position on the sprite sheet.
*   **frame\_count**: `8` - Total number of frames in this animation.
*   **frame\_width**: `12` - Width of each individual frame.
*   **frame\_height**: `19` - Height of each individual frame.
*   **frame\_wait**: `0.08` - Delay between frames in seconds.
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally on the sprite sheet.
*   **loop**: `1` - Indicates the animation will loop.

### `out` Animation

This animation likely represents the torch stand when the flame has been extinguished.

#### Key Attributes:

*   **name**: `out`
*   **pos\_x**: `0` - Starting X position on the sprite sheet.
*   **pos\_y**: `19` - Starting Y position on the sprite sheet. This indicates it's located below the `default` animation frames.
*   **frame\_count**: `1` - Total number of frames in this animation.
*   **frame\_width**: `12` - Width of each individual frame.
*   **frame\_height**: `19` - Height of each individual frame.
*   **frame\_wait**: `0.1` - Delay between frames in seconds.
*   **frames\_per\_row**: `4` - Number of frames arranged horizontally on the sprite sheet (though only one frame is used).
*   **loop**: `1` - Indicates the animation will loop.