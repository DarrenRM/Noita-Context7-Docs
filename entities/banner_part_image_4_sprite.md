---
title: Banner Part Image 4 Sprite
category: entities
---

# Banner Part Image 4 Sprite

This document describes the sprite configuration for a specific part of a banner entity in Noita.

## Sprite

The primary sprite for this entity part is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/banner/parts/image_4.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - The horizontal offset of the sprite from its origin.
*   **offset\_y**: `0` - The vertical offset of the sprite from its origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is active.

## Animation: `stand`

This section details the `stand` animation for the sprite.

### Key Attributes:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `11` - The width of each individual animation frame.
*   **frame\_height**: `24` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The number of game ticks to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).