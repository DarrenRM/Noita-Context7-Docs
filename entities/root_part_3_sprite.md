---
title: Root Part 3 Sprite
category: entities
---

# Root Part 3 Sprite

This document describes the sprite and animation data for a specific part of the "root" entity in Noita.

## Sprite

The primary sprite for this root part is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/root/root_parts/root.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default.

## Animation: `stand`

The `stand` animation is a simple, single-frame animation.

### Key Attributes:

*   **name**: `stand` - The identifier for this animation.
*   **pos\_x**: `16` - The X-coordinate of the sprite frame within the texture.
*   **pos\_y**: `0` - The Y-coordinate of the sprite frame within the texture.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `8` - The width of each individual frame.
*   **frame\_height**: `6` - The height of each individual frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the texture.
*   **loop**: `1` - Indicates that the animation should loop.