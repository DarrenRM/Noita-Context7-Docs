---
title: Ribbon Part Image 1 Sprite
category: entities
---

# Ribbon Part Image 1 Sprite

This document describes the sprite definition for a part of a ribbonverlet chain in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual appearance and animation of the entity part.

### Key Attributes

*   **filename**: `data/entities/verlet_chains/ribbon/parts/image_1.png` - The path to the sprite image file.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

### Animation: `stand`

The `<RectAnimation>` element defines a rectangular animation sequence.

#### Key Attributes

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `0` - The starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `5` - The width of each individual animation frame.
*   **frame\_height**: `3` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The duration (in frames) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).