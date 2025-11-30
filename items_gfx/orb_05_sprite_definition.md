---
title: Orb 05 Sprite Definition
category: items_gfx
---

---

# Orb 05 Sprite Definition

This document describes the sprite definition for "Orb 05" in Noita, focusing on its visual representation and animation.

## Sprite Attributes

The primary sprite attributes define the image file and its positioning.

*   **filename**: `data/items_gfx/orbs/orb_05.png` - The path to the sprite image.
*   **offset\_x**: `20` - Horizontal offset for the sprite.
*   **offset\_y**: `48` - Vertical offset for the sprite.
*   **default\_animation**: `default` - Specifies the name of the default animation to use.

## RectAnimation: "default"

This section details the animation sequence for the "default" state of the orb.

### Animation Properties

*   **name**: `default` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `7` - The total number of frames in the animation.
*   **frame\_width**: `40` - The width of each individual frame.
*   **frame\_height**: `50` - The height of each individual frame.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).