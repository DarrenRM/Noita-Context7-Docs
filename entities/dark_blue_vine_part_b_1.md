---
title: Dark Blue Vine Part B (1)
category: entities
---

# Dark Blue Vine Part B (1)

This entity defines a single segment of a dark blue vine, specifically the 'B' variant, numbered '1'. It's a visual component used in Noita'sverlet chain system to construct dynamic vine structures.

## Sprite Information

The sprite defines the visual appearance and animation of the vine segment.

### Sprite Attributes

*   **filename**: `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_b.png` - The texture file used for this sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default.

### Animation: `stand`

This animation defines the static appearance of the vine segment.

*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame in pixels.
*   **frame\_height**: `3` - The height of each individual frame in pixels.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).