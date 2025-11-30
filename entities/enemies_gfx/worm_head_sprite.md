---
title: Worm Head Sprite
category: entities/enemies_gfx
---

# Worm Head Sprite

This document describes the sprite data for the worm head enemy in Noita, focusing on its graphical representation and animations.

## Sprite Definition

The main `<Sprite>` element defines the base image and default animation for the worm head.

### Key Attributes:

*   **filename**: `data/enemies_gfx/worm_head.png` - The path to the sprite image file.
*   **offset_x**: `5` - Horizontal offset for the sprite.
*   **offset_y**: `7` - Vertical offset for the sprite.
*   **default_animation**: `"stand"` - The animation to play by default.

## Animations

The worm head has defined animations for different actions.

### `eat` Animation

*   **name**: `"eat"`
*   **frame\_count**: `7` - Total number of frames in this animation.
*   **frame\_height**: `13` - Height of each individual frame.
*   **frame\_wait**: `0.082` - Delay between frames in seconds.
*   **frame\_width**: `17` - Width of each individual frame.
*   **frames\_per\_row**: `7` - Number of frames arranged horizontally in the sprite sheet.
*   **pos\_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `1` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates if frames should be shrunk by one pixel.

### `stand` Animation

*   **name**: `"stand"`
*   **frame\_count**: `7` - Total number of frames in this animation.
*   **frame\_height**: `13` - Height of each individual frame.
*   **frame\_wait**: `0.082` - Delay between frames in seconds.
*   **frame\_width**: `17` - Width of each individual frame.
*   **frames\_per\_row**: `7` - Number of frames arranged horizontally in the sprite sheet.
*   **pos\_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `1` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates if frames should be shrunk by one pixel.