---
title: Flute Sprite Animation
category: items_gfx
---

# Flute Sprite Animation

This document describes the sprite animation data for the "flute" item in Noita, intended for AI-assisted modding.

## Sprite Definition

The core sprite definition for the flute.

### Key Attributes:

*   **filename**: `data/items_gfx/flute.png` - Specifies the image file containing the sprite.

## RectAnimation: "default"

Defines the animation sequence for the default state of the flute sprite.

### Key Attributes:

*   **name**: `default` - The identifier for this animation.
*   **pos\_x**: `1` - Starting X position within the sprite sheet.
*   **pos\_y**: `2` - Starting Y position within the sprite sheet.
*   **offset\_x**: `1` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `3.5` - Vertical offset for the sprite's origin.
*   **has\_offset**: `1` - Indicates that offsets are applied.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `11` - The width of each individual frame.
*   **frame\_height**: `7` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Specifies that the animation does not loop (plays once).