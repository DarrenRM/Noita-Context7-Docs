---
title: Orb Picked Sprite
category: items_gfx
---

---

# Orb Picked Sprite

This document describes the sprite definition for the "orb_picked" item in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual representation of the orb when it has been picked up.

### Key Attributes:

*   **filename**: `data/items_gfx/orbs/orb_picked.png` - The path to the image file used for the sprite.
*   **offset_x**: `20` - The horizontal offset of the sprite's origin.
*   **offset_y**: `48` - The vertical offset of the sprite's origin.
*   **default\_animation**: `default` - Specifies the name of the default animation to play.

## Animation Definition

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `default` - The name of this animation, referenced by the parent `<Sprite>` tag.
*   **pos\_x**: `0` - The starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `40` - The width of each individual animation frame.
*   **frame\_height**: `50` - The height of each individual animation frame.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).