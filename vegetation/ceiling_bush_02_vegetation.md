---
title: Ceiling Bush 02 Vegetation
category: data/vegetation
---

---

# Ceiling Bush 02 Vegetation

This document describes the `ceiling_bush_02.xml` file, which defines a specific type of vegetation entity in Noita.

## Sprite Definition

The `Sprite` element defines the visual appearance and animation of the vegetation.

### Key Attributes:

*   **filename**: `data/vegetation/ceiling_bush_02.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `36` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `30` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The name of the animation that plays by default.

## Animation Definition

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `vegetation_growth` - This is a special name that triggers a growing vegetation effect.
*   **pos\_x**: `0` - The X position of the animation's starting frame.
*   **pos\_y**: `0` - The Y position of the animation's starting frame.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `72` - The width of each animation frame.
*   **frame\_height**: `48` - The height of each animation frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).