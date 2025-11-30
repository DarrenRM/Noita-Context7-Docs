---
title: Dark Grass Patch 03 Sprite
category: data
---

---

# Dark Grass Patch 03 Sprite

This documentation describes the sprite definition for `grass_dark_patch_03.xml`, a vegetation asset in Noita.

## Sprite Definition

The core of this asset is the `<Sprite>` element, which defines the visual appearance and animation of the dark grass patch.

### Key Attributes:

*   **filename**: `data/vegetation/grass_dark_patch_03.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `10` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `9` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The name of the animation that plays by default. This is a special name that triggers a growing vegetation effect.

## Animation Definition

The `<RectAnimation>` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `20` - The width of each individual animation frame.
*   **frame\_height**: `10` - The height of each individual animation frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).