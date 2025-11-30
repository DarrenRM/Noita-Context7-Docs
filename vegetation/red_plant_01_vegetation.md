---
title: Red Plant 01 Vegetation
category: data/vegetation
---

---

# Red Plant 01 Vegetation

This document describes the `redplant_01.xml` file, which defines a specific type of vegetation in Noita.

## Sprite Definition

The primary element is `<Sprite>`, which defines the visual representation of the vegetation.

### Key Attributes:

*   **filename**: `data/vegetation/redplant_01.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `7` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `11` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The animation to play by default. This is a special name that triggers a growing vegetation effect.

## Animation Definition

The `<RectAnimation>` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `vegetation_growth` - The name of the animation.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `14` - The width of each individual frame.
*   **frame\_height**: `12` - The height of each individual frame.
*   **frame\_wait**: `999.0` - The duration (in frames) each frame is displayed. A high value indicates a slow or static display.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).