---
title: Orb 02 Sprite Definition
category: items_gfx
---

---

# Orb 02 Sprite Definition

This document details the sprite definition for "orb_02" in Noita, focusing on its graphical representation and animation.

## Sprite Attributes

The primary `<Sprite>` tag defines the visual asset and its basic positioning.

### Key Attributes:

*   **filename**: `data/items_gfx/orbs/orb_02.png` - The path to the sprite image file.
*   **offset\_x**: `20` - Horizontal offset for the sprite's anchor point.
*   **offset\_y**: `48` - Vertical offset for the sprite's anchor point.
*   **default\_animation**: `default` - Specifies the name of the default animation to play.

## Animation Definition

The `<RectAnimation>` tag defines how the sprite animates.

### Key Attributes:

*   **name**: `default` - The identifier for this animation.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame\_count**: `7` - The total number of frames in this animation.
*   **frame\_width**: `40` - The width of each individual frame.
*   **frame\_height**: `50` - The height of each individual frame.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).