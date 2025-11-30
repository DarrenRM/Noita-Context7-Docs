---
title: Meatvine Vine Part B4 Sprite
category: entities
---

# Meatvine Vine Part B4 Sprite

This document describes the sprite data for a specific part of the "meatvine" entity in Noita.

## Sprite

The `Sprite` element defines the visual appearance of the entity.

### Key Attributes

*   **filename**: `data/entities/verlet_chains/meatvine/vine_parts/vine_b.png` - The texture file used for this sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animation

The `RectAnimation` element defines the animation frames for the sprite.

### Key Attributes

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `12` - The X-coordinate of the top-left corner of the animation frame within the texture.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the animation frame within the texture.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each animation frame.
*   **frame\_height**: `3` - The height of each animation frame.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the texture.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).