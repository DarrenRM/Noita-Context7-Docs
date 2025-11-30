---
title: Small Lantern Flame Sprite
category: props_gfx
---

---

# Small Lantern Flame Sprite

This document describes the sprite data for the small lantern flame effect in Noita, used for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` element defines the texture file and its default animation.

### Key Attributes:

*   **filename**: `data/props_gfx/lantern_small_flame.png` - The path to the sprite sheet.
*   **offset\_x**: `4.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `12` - Vertical offset for the sprite's origin.
*   **default\_animation**: `default` - Specifies the animation to play by default.

## Animations

The sprite sheet contains multiple animations for the flame.

### `default` Animation

This animation represents the active, flickering state of the flame.

#### Key Attributes:

*   **name**: `default`
*   **pos\_x**: `0` - Starting X position on the sprite sheet.
*   **pos\_y**: `0` - Starting Y position on the sprite sheet.
*   **frame\_count**: `19` - Total number of frames in this animation.
*   **frame\_width**: `9` - Width of each individual frame.
*   **frame\_height**: `13` - Height of each individual frame.
*   **frame\_wait**: `0.07` - Time in seconds between frames.
*   **frames\_per\_row**: `19` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop.

### `out` Animation

This animation likely represents the flame being extinguished or in a dormant state.

#### Key Attributes:

*   **name**: `out`
*   **pos\_x**: `0` - Starting X position on the sprite sheet.
*   **pos\_y**: `13` - Starting Y position on the sprite sheet (below the `default` animation frames).
*   **frame\_count**: `1` - Only one frame for this animation.
*   **frame\_width**: `9` - Width of the frame.
*   **frame\_height**: `13` - Height of the frame.
*   **frame\_wait**: `0.09` - Time in seconds between frames (though only one frame).
*   **frames\_per\_row**: `1` - Number of frames arranged horizontally.
*   **loop**: `1` - Indicates that the animation should loop.