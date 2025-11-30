---
title: Dark Ghost Skull Sprite Data
category: entities/enemies_gfx
---

# Dark Ghost Skull Sprite Data

This document details the sprite data for the Dark Ghost Skull enemy in Noita, focusing on its visual animations.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and its default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/darkghost_skull.png` - The path to the sprite sheet.
*   **offset\_x**: `24` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `24` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The sprite sheet contains definitions for different animations.

### `stand` Animation

This animation represents the Dark Ghost Skull's idle or standing state.

#### Key Attributes:

*   **name**: `"stand"`
*   **pos\_x**: `0` - Starting X position on the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y position on the sprite sheet for this animation.
*   **frame\_count**: `4` - Total number of frames in this animation.
*   **frame\_width**: `48` - Width of each individual frame.
*   **frame\_height**: `48` - Height of each individual frame.
*   **frame\_wait**: `0.08` - Time in seconds between frames.
*   **frames\_per\_row**: `4` - Number of frames per row in the sprite sheet.
*   **loop**: `1` - Indicates the animation loops (1 for true, 0 for false).

### `blink` Animation

This animation likely represents a blinking or subtle visual effect for the skull.

#### Key Attributes:

*   **name**: `"blink"`
*   **pos\_x**: `0` - Starting X position on the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y position on the sprite sheet for this animation.
*   **frame\_count**: `11` - Total number of frames in this animation.
*   **frame\_width**: `48` - Width of each individual frame.
*   **frame\_height**: `48` - Height of each individual frame.
*   **frame\_wait**: `0.08` - Time in seconds between frames.
*   **frames\_per\_row**: `11` - Number of frames per row in the sprite sheet.
*   **loop**: `0` - Indicates the animation does not loop (0 for false).