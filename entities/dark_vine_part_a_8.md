---
title: Dark Vine Part A (8)
category: entities
---

---

# Dark Vine Part A (8)

This entity defines a segment of a dark vine, specifically the eighth part in the sequence. It's a visual component used in Noita'sverlet chain system for creating vine-like structures.

## Sprite

The sprite defines the visual appearance of this vine segment.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts/vine_dark_a.png` - The texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

### Animation: `stand`

This defines the animation frames for the vine segment.

*   **name**: `"stand"`
*   **pos\_x**: `28` - X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - Total number of frames in the animation.
*   **frame\_width**: `4` - Width of a single animation frame.
*   **frame\_height**: `3` - Height of a single animation frame.
*   **frame\_wait**: `1` - Delay between frames in game ticks.
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Whether the animation should loop (1 for true, 0 for false).