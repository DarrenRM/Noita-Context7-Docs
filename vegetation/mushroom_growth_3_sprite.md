---
title: Mushroom Growth 3 Sprite
category: data/vegetation
---

---

# Mushroom Growth 3 Sprite

This document describes the sprite and animation data for "Mushroom Growth 3" in Noita, intended for AI-assisted modding.

## Sprite Information

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/mushroom_growth_3.png` - Specifies the image file for the sprite.
*   **offset\_x**: `16` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `33` - Vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The name of the animation to play by default. This is a special name that triggers a growing vegetation effect.

## Animation Data

The animation is defined by the `<RectAnimation>` tag, named `vegetation_growth`.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `8` - The total number of frames in the animation.
*   **frame\_width**: `32` - The width of each individual frame.
*   **frame\_height**: `34` - The height of each individual frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).