---
title: Dark Blue Vine Part B (5)
category: entities
---

# Dark Blue Vine Part B (5)

This entity defines a single segment of a dark blue vine, specifically the fifth variation in the sequence. It utilizes a sprite and animation to render its appearance.

## Sprite

The sprite definition points to the texture file and specifies its rendering properties.

*   **filename**: `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_b.png` - The texture file containing the vine segment's visual data.
*   **offset\_x**: `0` - Horizontal offset for the sprite.
*   **offset\_y**: `0` - Vertical offset for the sprite.
*   **default\_animation**: `stand` - The animation to play by default.

### Animation: `stand`

This section details the animation used for the vine segment.

*   **name**: `stand` - The name of this animation.
*   **pos\_x**: `16` - The X-coordinate within the sprite sheet for the animation's starting frame.
*   **pos\_y**: `0` - The Y-coordinate within the sprite sheet for the animation's starting frame.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame.
*   **frame\_height**: `3` - The height of each individual frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).