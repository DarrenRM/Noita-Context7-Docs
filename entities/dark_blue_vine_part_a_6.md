---
title: Dark Blue Vine Part A (6)
category: entities
---

---

# Dark Blue Vine Part A (6)

This entity defines a single segment of a dark blue vine, specifically part 'A' and designated as the 6th variation. It's a visual component used in Noita'sverlet chain system for creating dynamic vine structures.

## Sprite Information

The visual representation of this vine segment is handled by a `Sprite` component.

### Key Sprite Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_a.png` - The texture file used for this sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animation Details

The `Sprite` component utilizes a `RectAnimation` to define its visual states.

### Key Animation Attributes (`stand`):

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `20` - The X-coordinate within the texture atlas for the animation's starting frame.
*   **pos\_y**: `0` - The Y-coordinate within the texture atlas for the animation's starting frame.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame.
*   **frame\_height**: `3` - The height of each individual frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the texture.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).