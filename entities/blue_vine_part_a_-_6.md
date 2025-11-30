---
title: Blue Vine Part A - 6
category: entities
---

---

# Blue Vine Part A - 6

This entity defines a segment of a blue vine, specifically the 'A' type, and is the sixth variation in its sequence. It utilizes a sprite for its visual representation and defines its animation properties.

## Sprite

The visual appearance of this vine segment is determined by the `Sprite` component.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts_blue/vine_a.png` - The texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is spawned.

## Animation

The `RectAnimation` component defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `"stand"` - The name of this specific animation.
*   **pos\_x**: `20` - The X-coordinate within the sprite sheet for the animation's starting frame.
*   **pos\_y**: `0` - The Y-coordinate within the sprite sheet for the animation's starting frame.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame in pixels.
*   **frame\_height**: `3` - The height of each individual frame in pixels.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).