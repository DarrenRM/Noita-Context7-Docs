---
title: Chandelier Flames Sprite
category: props_gfx
---

# Chandelier Flames Sprite

This document describes the sprite data for the chandelier flames in Noita, used for visual effects.

## Sprite Definition

The main `<Sprite>` tag defines the texture file and its default animation.

### Key Attributes:

*   **filename**: `data/props_gfx/chandelier_flames.png` - The path to the sprite sheet.
*   **offset\_x**: `8.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `9.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `default` - The animation to play by default.

## Animations

The sprite sheet contains multiple animations defined by `<RectAnimation>` tags.

### `default` Animation

This animation represents the active, flickering flames of the chandelier.

*   **name**: `default`
*   **pos\_x**: `0` - Starting X position on the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y position on the sprite sheet for this animation.
*   **frame\_count**: `6` - Total number of frames in this animation.
*   **frame\_width**: `17` - Width of each individual frame.
*   **frame\_height**: `19` - Height of each individual frame.
*   **frame\_wait**: `0.1` - Time in seconds between frames.
*   **frames\_per\_row**: `6` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates the animation loops (1 for true, 0 for false).

### `out` Animation

This animation likely represents the flames being extinguished or a static state.

*   **name**: `out`
*   **pos\_x**: `0` - Starting X position on the sprite sheet for this animation.
*   **pos\_y**: `19` - Starting Y position on the sprite sheet for this animation.
*   **frame\_count**: `1` - Total number of frames in this animation.
*   **frame\_width**: `17` - Width of each individual frame.
*   **frame\_height**: `19` - Height of each individual frame.
*   **frame\_wait**: `0.1` - Time in seconds between frames.
*   **frames\_per\_row**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates the animation loops.