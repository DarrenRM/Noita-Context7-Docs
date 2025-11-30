---
title: Lantern Flame Sprite
category: props_gfx
---

# Lantern Flame Sprite

This document describes the sprite data for the lantern flame effect in Noita.

## Sprite Definition

The main `<Sprite>` tag defines the texture file and its default animation.

### Key Attributes:

*   **filename**: `data/props_gfx/lantern_flame.png` - The path to the sprite texture.
*   **offset\_x**: `4.5` - Horizontal offset for the sprite.
*   **offset\_y**: `12` - Vertical offset for the sprite.
*   **default\_animation**: `default` - The animation to play by default.

## Animations

The sprite contains two defined animations: `default` and `out`.

### `default` Animation

This animation represents the standard flickering flame.

#### Key Attributes:

*   **name**: `default`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `19` - Total number of frames in the animation.
*   **frame\_width**: `9` - Width of each individual frame.
*   **frame\_height**: `13` - Height of each individual frame.
*   **frame\_wait**: `0.07` - Time in seconds between frames.
*   **frames\_per\_row**: `19` - Number of frames in a single row of the sprite sheet.
*   **loop**: `1` - Indicates the animation loops (1 for true).

### `out` Animation

This animation likely represents the flame being extinguished or a static frame.

#### Key Attributes:

*   **name**: `out`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `13` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - Total number of frames in the animation.
*   **frame\_width**: `9` - Width of each individual frame.
*   **frame\_height**: `13` - Height of each individual frame.
*   **frame\_wait**: `0.09` - Time in seconds between frames.
*   **frames\_per\_row**: `1` - Number of frames in a single row of the sprite sheet.
*   **loop**: `1` - Indicates the animation loops (1 for true).