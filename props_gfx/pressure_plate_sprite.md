---
title: Pressure Plate Sprite
category: props_gfx
---

# Pressure Plate Sprite

This document describes the sprite data for the pressure plate prop in Noita, focusing on its visual representation and animations.

## Sprite Definition

The main `Sprite` element defines the base image and default animation for the pressure plate.

### Key Attributes:

*   **filename**: `data/props_gfx/pressure_plate.png` - The path to the sprite image file.
*   **offset\_x**: `12` - Horizontal offset for the sprite.
*   **offset\_y**: `1` - Vertical offset for the sprite.
*   **default\_animation**: `"up"` - The animation to play by default when the sprite is active.

## Animations

The pressure plate has two distinct animations: `"up"` (default, unpressed) and `"down"` (pressed).

### `RectAnimation` - "up"

This animation represents the unpressed state of the pressure plate.

*   **name**: `"up"`
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet.
*   **frame\_count**: `"1"` - Number of frames in this animation.
*   **frame\_width**: `"24"` - Width of each frame.
*   **frame\_height**: `"2"` - Height of each frame.
*   **frame\_wait**: `"0.1"` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `"4"` - Number of frames per row in the sprite sheet.
*   **loop**: `"0"` - Whether the animation should loop (0 for no loop).

### `RectAnimation` - "down"

This animation represents the pressed state of the pressure plate.

*   **name**: `"down"`
*   **pos\_x**: `"24"` - Starting X position within the sprite sheet (shifted from the "up" state).
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet.
*   **frame\_count**: `"1"` - Number of frames in this animation.
*   **frame\_width**: `"24"` - Width of each frame.
*   **frame\_height**: `"2"` - Height of each frame.
*   **frame\_wait**: `"0.1"` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `"4"` - Number of frames per row in the sprite sheet.
*   **loop**: `"0"` - Whether the animation should loop (0 for no loop).