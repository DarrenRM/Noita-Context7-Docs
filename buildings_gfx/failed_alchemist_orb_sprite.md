---
title: Failed Alchemist Orb Sprite
category: buildings_gfx
---

# Failed Alchemist Orb Sprite

This documentation describes the sprite definition for the "failed alchemist orb" building graphic in Noita.

## Sprite Definition

The primary `<Sprite>` element defines the visual asset for the orb.

### Key Attributes:

*   **filename**: `data/buildings_gfx/failed_alchemist_orb.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `12` - Vertical offset of the sprite's origin.
*   **default\_animation**: `default` - Sets the default animation to be played.

## Animation Definition

The `<RectAnimation>` element defines the animation sequence for the orb.

### Key Attributes:

*   **name**: `default` - The name of this animation.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame\_count**: `6` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame in pixels.
*   **frame\_height**: `16` - The height of each individual frame in pixels.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).