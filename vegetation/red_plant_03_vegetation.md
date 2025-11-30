---
title: Red Plant 03 Vegetation
category: data/vegetation
---

---

# Red Plant 03 Vegetation

This document describes the `redplant_03.xml` file, which defines a specific type of vegetation in Noita.

## Sprite Definition

The primary element is the `<Sprite>` tag, which defines the visual representation of the vegetation.

### Key Attributes:

*   **filename**: `data/vegetation/redplant_03.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `7` - Horizontal offset of the sprite.
*   **offset\_y**: `11` - Vertical offset of the sprite.
*   **default\_animation**: `vegetation_growth` - The animation to play by default. This is a special name that triggers a growing vegetation effect.

## Animation Details

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `vegetation_growth` - The name of this specific animation.
*   **pos\_x**: `0` - Starting X position of the animation frames.
*   **pos\_y**: `0` - Starting Y position of the animation frames.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `14` - The width of each individual frame.
*   **frame\_height**: `12` - The height of each individual frame.
*   **frame\_wait**: `999.0` - The duration (in game frames) each frame is displayed. A high value indicates a slow or static animation.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).