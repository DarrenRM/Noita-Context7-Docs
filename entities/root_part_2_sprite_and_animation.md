---
title: Root Part 2 Sprite and Animation
category: entities
---

# Root Part 2 Sprite and Animation

This document describes the sprite and animation data for a specific part of the "root" entity in Noita.

## Sprite

The `Sprite` element defines the visual appearance of the entity part.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/root/root_parts/root.png` - Path to the sprite image file.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation

The `RectAnimation` element defines a rectangular animation sequence.

### Key Attributes:

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `8` - X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `8` - The width of each individual animation frame.
*   **frame\_height**: `6` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames that fit horizontally in a single row of the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).