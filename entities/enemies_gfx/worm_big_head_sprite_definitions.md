---
title: Worm Big Head Sprite Definitions
category: entities/enemies_gfx
---

# Worm Big Head Sprite Definitions

This document details the sprite definitions for the "worm_big_head" enemy in Noita, focusing on its visual representation and animations.

## Sprite Attributes

The main `<Sprite>` tag defines the base image and its properties.

*   **filename**: `data/enemies_gfx/worm_big_head.png` - The path to the sprite sheet.
*   **offset\_x**: `14` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `12` - Vertical offset for the sprite's origin.
*   **default\_animation**: `stand` - The animation to play by default.

## Animations

The `<RectAnimation>` tags define specific animations for the sprite.

### `stand` Animation

This animation defines the "standing" or idle state of the worm's head.

*   **name**: `stand`
*   **frame\_count**: `4` - Total number of frames in this animation.
*   **frame\_width**: `29` - Width of each individual frame.
*   **frame\_height**: `26` - Height of each individual frame.
*   **frames\_per\_row**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.082` - Delay between frames in seconds.
*   **pos\_x**: `0` - X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: `1` - Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates if frames should be shrunk by one pixel.

### `eat` Animation

This animation defines the "eating" state of the worm's head.

*   **name**: `eat`
*   **frame\_count**: `4` - Total number of frames in this animation.
*   **frame\_width**: `29` - Width of each individual frame.
*   **frame\_height**: `26` - Height of each individual frame.
*   **frames\_per\_row**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.082` - Delay between frames in seconds.
*   **pos\_x**: `0` - X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: `1` - Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates if frames should be shrunk by one pixel.