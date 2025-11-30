---
title: Orb 08 Sprite Definition
category: items_gfx
---

```

# Orb 08 Sprite Definition

This document details the sprite definition for Orb 08, a graphical asset used in Noita.

## Sprite Attributes

The primary `<Sprite>` element defines the visual representation of the orb.

### Key Attributes:

*   **filename**: `data/items_gfx/orbs/orb_08.png` - The path to the image file containing the orb's graphics.
*   **offset\_x**: `20` - Horizontal offset for the sprite's position.
*   **offset\_y**: `48` - Vertical offset for the sprite's position.
*   **default\_animation**: `default` - Specifies the name of the default animation to be used.

## Animation Definition

The `<RectAnimation>` element defines how the sprite animates.

### Key Attributes:

*   **name**: `default` - The name of this animation, referenced by the `<Sprite>` element.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `7` - The total number of frames in the animation.
*   **frame\_width**: `40` - The width of each individual frame.
*   **frame\_height**: `50` - The height of each individual frame.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).