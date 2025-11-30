---
title: Banner Part Image 3 Sprite
category: entities
---

# Banner Part Image 3 Sprite

This document describes the sprite and animation data for a specific part of a banner entity in Noita.

## Sprite

The `<Sprite>` element defines the visual appearance and animation of the entity part.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/banner/parts/image_3.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - The horizontal offset of the sprite.
*   **offset\_y**: `0` - The vertical offset of the sprite.
*   **default\_animation**: `stand` - The name of the animation that plays by default.

## Animation

The `<RectAnimation>` element defines a specific animation sequence.

### Key Attributes:

*   **name**: `stand` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - The starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `8` - The width of each individual frame.
*   **frame\_height**: `24` - The height of each individual frame.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).