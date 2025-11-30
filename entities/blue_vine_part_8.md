---
title: Blue Vine Part 8
category: entities
---

# Blue Vine Part 8

This document describes the entity configuration for a specific part of a blue vine in Noita.

## Sprite

The sprite component defines the visual appearance of the vine part.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts_blue/vine_b.png` - The texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation to play by default.

### Animation: `stand`

This defines the animation sequence for the vine part.

*   **name**: `stand`
*   **pos\_x**: `28` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `1` - Total number of frames in the animation.
*   **frame\_width**: `4` - Width of each individual frame.
*   **frame\_height**: `3` - Height of each individual frame.
*   **frame\_wait**: `1` - Delay between frames in game ticks.
*   **frames\_per\_row**: `8` - Number of frames in a single row of the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).