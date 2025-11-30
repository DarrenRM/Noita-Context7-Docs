---
title: Healer Drone Emissive Sprite
category: entities
---

---

# Healer Drone Emissive Sprite

This document describes the sprite data for the Healer Drone's emissive texture in Noita.

## Sprite Definition

The main `<Sprite>` tag defines the base texture and its properties.

### Key Attributes:

*   **filename**: `data/enemies_gfx/healerdrone_emissive.png` - The path to the sprite texture file.
*   **offset\_x**: `5.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `4` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The `<RectAnimation>` tags define individual animations for the sprite.

### `stand` Animation

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `"1"` - The total number of frames in this animation.
*   **frame\_width**: `"12"` - The width of each individual frame.
*   **frame\_height**: `"8"` - The height of each individual frame.
*   **frame\_wait**: `"0.2"` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `"1"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates if the animation should loop (1 for true, 0 for false).