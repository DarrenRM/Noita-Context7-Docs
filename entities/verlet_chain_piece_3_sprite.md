---
title: Verlet Chain Piece 3 Sprite
category: entities
---

# Verlet Chain Piece 3 Sprite

This document describes the sprite data for the third piece of the Verlet chain used by the boss centipede in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/verlet_chains/verlet_piece_3.png` - Specifies the image file for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

### `stand` Animation

This is the only defined animation for this sprite.

#### Key Attributes:

*   **name**: `"stand"` - The name of the animation.
*   **pos\_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `7` - The width of each individual frame.
*   **frame\_height**: `7` - The height of each individual frame.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).