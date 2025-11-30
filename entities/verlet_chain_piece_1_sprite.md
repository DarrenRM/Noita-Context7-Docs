---
title: Verlet Chain Piece 1 Sprite
category: entities
---

# Verlet Chain Piece 1 Sprite

This document describes the sprite and animation data for the first piece of the boss centipede's "verlet chain" in Noita.

## Sprite

The sprite defines the visual appearance and basic positioning of the entity.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/verlet_chains/verlet_piece_1.png` - Path to the sprite image.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation to play by default.

## Animation

This section defines the animation sequences for the sprite.

### `stand` Animation:

This is the primary animation for the verlet chain piece.

#### Key Attributes:

*   **name**: `stand` - The name of this animation.
*   **pos\_x**: `0` - X-coordinate of the sprite's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the sprite's top-left corner within the sprite sheet.
*   **frame\_count**: `1` - Total number of frames in the animation.
*   **frame\_width**: `7` - Width of each individual frame.
*   **frame\_height**: `7` - Height of each individual frame.
*   **frame\_wait**: `1` - Delay between frames in game ticks.
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).