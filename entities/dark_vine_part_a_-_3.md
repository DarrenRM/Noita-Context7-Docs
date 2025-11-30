---
title: Dark Vine Part A - 3
category: entities
---

# Dark Vine Part A - 3

This entity defines a segment of a dark vine, specifically the third part in a sequence. It utilizes a sprite and animation to render its appearance.

## Sprite

The sprite for this vine part is defined by the following attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts/vine_dark_a.png` - The texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation: "stand"

This section details the animation used for the vine part.

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `8` - X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each animation frame.
*   **frame\_height**: `3` - The height of each animation frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).