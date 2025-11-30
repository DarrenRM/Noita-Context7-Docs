---
title: Tail Part 2 Entity
category: entities
---

# Tail Part 2 Entity

This document describes the `tail_2.xml` entity, which defines a segment of a tail for Noita.

## Sprite

The primary visual representation of this tail segment.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/tail/tail_parts/tail.png` - The texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset for the sprite.
*   **offset\_y**: `2` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

### Animations

#### `stand` Animation

*   **name**: `"stand"`
*   **pos\_x**: `2` - X-coordinate of the sprite's top-left corner within the texture.
*   **pos\_y**: `0` - Y-coordinate of the sprite's top-left corner within the texture.
*   **frame\_count**: `1` - Total number of frames in the animation.
*   **frame\_width**: `2` - Width of each animation frame.
*   **frame\_height**: `4` - Height of each animation frame.
*   **frame\_wait**: `1` - Delay between frames in game ticks.
*   **frames\_per\_row**: `8` - Number of frames in a single row of the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).