---
title: Monk Cape Part 2 Sprite
category: entities
---

# Monk Cape Part 2 Sprite

This document describes the sprite data for a part of the Monk Cape entity in Noita.

## Sprite

The primary sprite for this entity part is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/monk_cape/parts/cape_2.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - The horizontal offset of the sprite.
*   **offset\_y**: `0` - The vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default.

## Animation: `stand`

The `stand` animation defines how the sprite is displayed over time.

### Key Attributes:

*   **name**: `stand` - The name of this animation.
*   **pos\_x**: `0` - The starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - The starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `8` - The width of each individual frame.
*   **frame\_height**: `24` - The height of each individual frame.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames that fit horizontally in a single row of the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).