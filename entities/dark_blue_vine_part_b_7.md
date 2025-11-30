---
title: Dark Blue Vine Part B (7)
category: entities
---

# Dark Blue Vine Part B (7)

This entity defines a specific segment of a dark blue vine, likely used in Noita's world generation or as a destructible element. It utilizes a sprite with a single animation frame.

## Sprite

The visual representation of this vine segment.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_b.png` - Specifies the texture file used.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation: `stand`

Defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `24` - The X-coordinate of the sprite's frame within the texture atlas.
*   **pos\_y**: `0` - The Y-coordinate of the sprite's frame within the texture atlas.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of a single animation frame.
*   **frame\_height**: `3` - The height of a single animation frame.
*   **frame\_wait**: `1` - The duration each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the texture atlas.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).