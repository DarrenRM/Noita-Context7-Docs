---
title: Blue Vine Part B6 Sprite
category: entities
---

# Blue Vine Part B6 Sprite

This document describes the sprite data for a specific part of a blue vine entity in Noita.

## Sprite

The sprite for this vine part uses a single image file and a basic animation.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts_blue/vine_b.png` - The texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default.

### Animation: `stand`

This animation defines how the sprite is displayed.

#### Key Attributes:

*   **name**: `stand` - The name of the animation.
*   **pos\_x**: `20` - X-coordinate within the sprite sheet for the animation's starting frame.
*   **pos\_y**: `0` - Y-coordinate within the sprite sheet for the animation's starting frame.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `4` - The width of each individual frame.
*   **frame\_height**: `3` - The height of each individual frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed.
*   **frames\_per\_row**: `8` - The number of frames that fit horizontally in a single row of the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).