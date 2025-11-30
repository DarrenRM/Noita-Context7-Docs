---
title: Banner Sprite Animation
category: props_gfx
---

---

# Banner Sprite Animation

This document describes the sprite animation data for the 'banner' prop in Noita.

## Sprite Definition

The main `<Sprite>` element defines the visual asset and its default animation.

### Key Attributes:

*   **filename**: `data/props_gfx/banner.png` - The path to the sprite sheet image.
*   **offset\_x**: `12` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `30` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation: "stand"

The `<RectAnimation>` element defines a specific animation sequence.

### Key Attributes:

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `"0"` - The X-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **pos\_y**: `"0"` - The Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
*   **frame\_count**: `"7"` - The total number of frames in this animation.
*   **frame\_width**: `"32"` - The width of each individual frame.
*   **frame\_height**: `"32"` - The height of each individual frame.
*   **frame\_wait**: `"0.11"` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `"7"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates if the animation should loop (1 for true, 0 for false).