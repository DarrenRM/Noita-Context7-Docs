---
title: Candle 3 Emissive Sprite
category: props_gfx
---

# Candle 3 Emissive Sprite

This document describes the sprite data for the "candle_3_emissive" prop in Noita. It defines the visual appearance and animations for this prop.

## Sprite Definition

The main `<Sprite>` element defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/props_gfx/candle_3_emissive.png` - The path to the sprite sheet image.
*   **offset\_x**: `4.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `13` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"default"` - Specifies the animation to play by default.

## Animations

The `<Sprite>` element contains one or more `<RectAnimation>` elements, each defining a distinct animation.

### Animation: `default`

This animation represents the standard, lit state of the candle.

#### Key Attributes:

*   **name**: `"default"`
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `"4"` - The total number of frames in this animation.
*   **frame\_width**: `"9"` - The width of each individual frame.
*   **frame\_height**: `"14"` - The height of each individual frame.
*   **frame\_wait**: `"0.1"` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `"4"` - How many frames are arranged horizontally in the sprite sheet for this animation.
*   **loop**: `"1"` - Indicates that the animation should loop (1 for true, 0 for false).

### Animation: `out`

This animation likely represents the candle being extinguished or in an "out" state.

#### Key Attributes:

*   **name**: `"out"`
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `"14"` - Starting Y position within the sprite sheet for this animation. This suggests the "out" frames are located below the "default" frames in the sprite sheet.
*   **frame\_count**: `"1"` - This animation consists of a single frame.
*   **frame\_width**: `"9"` - The width of the frame.
*   **frame\_height**: `"14"` - The height of the frame.
*   **frame\_wait**: `"0.1"` - The duration each frame is displayed.
*   **frames\_per\_row**: `"1"` - Only one frame per row.
*   **loop**: `"1"` - The animation will loop (though with only one frame, this is less impactful).