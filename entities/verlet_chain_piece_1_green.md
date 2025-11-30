---
title: Verlet Chain Piece 1 (Green)
category: entities
---

# Verlet Chain Piece 1 (Green)

This entity represents a single segment of the "verlet chain" used by a boss centipede. It's a small, green sprite with a simple animation.

## Sprite

The sprite defines the visual appearance and animation of the entity.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/verlet_chains/verlet_piece_1_green.png` - Path to the sprite image.
*   **offset\_x**, **offset\_y**: `0`, `0` - Defines the sprite's origin point.
*   **default\_animation**: `stand` - The animation to play by default.

### Animation: `stand`

This is a basic, single-frame animation.

#### Key Attributes:

*   **frame\_count**: `1` - Number of frames in the animation.
*   **frame\_width**, **frame\_height**: `7`, `7` - Dimensions of each frame in pixels.
*   **frame\_wait**: `1` - Delay between frames (in game ticks).
*   **frames\_per\_row**: `8` - How many frames are arranged horizontally in the sprite sheet.
*   **loop**: `1` - Whether the animation should loop.