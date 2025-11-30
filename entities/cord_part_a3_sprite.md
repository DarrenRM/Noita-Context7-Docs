---
title: Cord Part A3 Sprite
category: entities
---

# Cord Part A3 Sprite

This document describes the sprite and animation data for `cord_a_3.xml`, a component of a verlet chain cord in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/cords/cord_parts/cord_a.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `0` - The horizontal offset of the sprite from its origin.
*   **offset\_y**: `0` - The vertical offset of the sprite from its origin.
*   **default\_animation**: `stand` - The name of the animation that plays by default.

## Animation: `stand`

The `stand` animation defines how the sprite is displayed and animated.

### Key Attributes:

*   **name**: `stand` - The identifier for this animation.
*   **pos\_x**: `12` - The X-coordinate within the sprite sheet for the animation's starting frame.
*   **pos\_y**: `0` - The Y-coordinate within the sprite sheet for the animation's starting frame.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame in pixels.
*   **frame\_height**: `3` - The height of each individual frame in pixels.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).