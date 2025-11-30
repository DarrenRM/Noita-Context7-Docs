---
title: Banner Part Image 2 Sprite
category: entities
---

# Banner Part Image 2 Sprite

This document describes the sprite configuration for a specific part of a banner entity in Noita.

## Sprite Configuration

The `<Sprite>` element defines the visual appearance and animation of the entity part.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/banner/parts/image_2.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - The horizontal offset of the sprite from its origin.
*   **offset\_y**: `0` - The vertical offset of the sprite from its origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is active.

## Animation Details

The `<RectAnimation>` element defines the properties of a specific animation.

### Key Attributes for "stand" animation:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - The starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `8` - The width of each individual frame in pixels.
*   **frame\_height**: `24` - The height of each individual frame in pixels.
*   **frame\_wait**: `1` - The number of game ticks to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames that fit horizontally in a single row of the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).