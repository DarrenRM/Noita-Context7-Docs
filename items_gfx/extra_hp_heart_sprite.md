---
title: Extra HP Heart Sprite
category: items_gfx
---

# Extra HP Heart Sprite

This documentation describes the sprite definition for the "Extra HP Heart" item in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual representation of the item.

### Key Attributes:

*   **filename**: `data/items_gfx/heart_extrahp.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset for the sprite's position.
*   **offset\_y**: `21` - Vertical offset for the sprite's position.
*   **default\_animation**: `"default"` - The name of the default animation to play.

## Animation Definition

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `"default"` - The name of this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `4` - The total number of frames in the animation.
*   **frame\_width**: `20` - The width of each individual frame.
*   **frame\_height**: `20` - The height of each individual frame.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).