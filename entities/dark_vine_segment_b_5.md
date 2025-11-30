---
title: Dark Vine Segment B (5)
category: entities
---

# Dark Vine Segment B (5)

This entity defines a segment of a dark vine, specifically the fifth variation in the `vine_dark_b` chain. It's a visual component used in the game's physics and rendering system.

## Sprite Information

The primary visual representation of this vine segment is defined by the `<Sprite>` tag.

### Key Sprite Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts/vine_dark_b.png` - Specifies the texture file used for this sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default when the entity is active.

## Animation Details

The `<RectAnimation>` tag describes the animation frames for this sprite.

### Key Animation Attributes:

*   **name**: `stand` - The name of this animation.
*   **pos\_x**: `16` - The X-coordinate within the sprite sheet where the animation frames begin.
*   **pos\_y**: `0` - The Y-coordinate within the sprite sheet where the animation frames begin.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual animation frame.
*   **frame\_height**: `3` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

This entity is a simple visual element, likely used in conjunction with other entities to form a complete vine structure. Its primary function is to display a small, static segment of the dark vine.