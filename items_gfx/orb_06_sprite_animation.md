---
title: Orb 06 Sprite Animation
category: items_gfx
---

---

# Orb 06 Sprite Animation

This documentation describes the sprite and animation data for Orb 06 in Noita.

## Sprite Data

The primary sprite for Orb 06 is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/items_gfx/orbs/orb_06.png` - The path to the sprite image file.
*   **offset_x**: `20` - Horizontal offset for the sprite.
*   **offset_y**: `48` - Vertical offset for the sprite.
*   **default\_animation**: `default` - Specifies the name of the default animation to play.

## Animation Data

The animation for Orb 06 is defined within the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `default` - The name of this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `7` - The total number of frames in the animation.
*   **frame\_width**: `40` - The width of each individual frame.
*   **frame\_height**: `50` - The height of each individual frame.
*   **frame\_wait**: `0.12` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).