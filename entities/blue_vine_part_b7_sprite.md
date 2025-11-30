---
title: Blue Vine Part B7 Sprite
category: entities
---

# Blue Vine Part B7 Sprite

This document describes the sprite data for a specific part of a blue vine entity in Noita.

## Sprite

The primary sprite for this vine part is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts_blue/vine_b.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default.

## Animation: `stand`

The `stand` animation defines how the sprite is displayed.

### Key Attributes:

*   **name**: `stand` - The name of this animation.
*   **pos\_x**: `24` - The X-coordinate of the top-left corner of the sprite frame within the texture.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the sprite frame within the texture.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame.
*   **frame\_height**: `3` - The height of each individual frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed.
*   **frames\_per\_row**: `8` - The number of frames that fit horizontally in the texture.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).