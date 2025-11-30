---
title: Blue Vine Part A3 Sprite
category: entities
---

# Blue Vine Part A3 Sprite

This documentation describes the sprite data for a specific part of a blue vine entity in Noita.

## Sprite

The primary sprite for this vine part is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts_blue/vine_a.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `0` - The horizontal offset of the sprite.
*   **offset\_y**: `0` - The vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animation

The sprite utilizes a single animation named "stand".

### Key Attributes:

*   **name**: `"stand"` - The name of the animation.
*   **pos\_x**: `8` - The starting X position within the sprite sheet for this animation frame.
*   **pos\_y**: `0` - The starting Y position within the sprite sheet for this animation frame.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual animation frame.
*   **frame\_height**: `3` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of animation frames that fit horizontally in a single row of the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).