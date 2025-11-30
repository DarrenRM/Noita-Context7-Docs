---
title: Blue Vine Part B5 Sprite
category: entities
---

---

# Blue Vine Part B5 Sprite

This document describes the sprite data for a specific part of a blue vine entity in Noita.

## Sprite Definition

The `Sprite` element defines the visual appearance of the entity.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts_blue/vine_b.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default.

## Animation Definition

The `RectAnimation` element defines the animation frames for the sprite.

### Key Attributes:

*   **name**: `stand` - The name of this animation.
*   **pos\_x**: `16` - The starting X coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y coordinate of the animation frames within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual animation frame.
*   **frame\_height**: `3` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The duration (in frames) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).