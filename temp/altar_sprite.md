---
title: Altar Sprite
category: data
---

---

# Altar Sprite

This documentation describes the sprite definition for the Altar entity in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual representation of the Altar.

### Key Attributes:

*   **filename**: `data/temp/altar.png` - The path to the sprite image file.
*   **offset\_x**: `32` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `32` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The `<RectAnimation>` tag defines the individual animations for the sprite.

### Stand Animation:

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `3` - The total number of frames in this animation.
*   **frame\_width**: `32` - The width of each individual frame.
*   **frame\_height**: `32` - The height of each individual frame.
*   **frame\_wait**: `0.09` - The time in seconds to wait between frames.
*   **frames\_per\_row**: `3` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).