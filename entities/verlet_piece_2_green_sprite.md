---
title: Verlet Piece 2 (Green) Sprite
category: entities
---

# Verlet Piece 2 (Green) Sprite

This document describes the sprite data for a green "verlet piece" used by the boss centipede in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/verlet_chains/verlet_piece_2_green.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default.

## Animations

The entity has one defined animation.

### `stand` Animation

*   **name**: `stand`
*   **pos\_x**: `0` - X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - Total number of frames in the animation.
*   **frame\_width**: `7` - Width of each individual animation frame.
*   **frame\_height**: `7` - Height of each individual animation frame.
*   **frame\_wait**: `1` - Delay between frames in game ticks.
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).