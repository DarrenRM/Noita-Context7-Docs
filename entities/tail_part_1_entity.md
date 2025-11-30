---
title: Tail Part 1 Entity
category: entities
---

---

# Tail Part 1 Entity

This document describes the `tail_1.xml` entity, which defines a single segment of a tail in Noita.

## Sprite

The `Sprite` element defines the visual representation of the tail segment.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/tail/tail_parts/tail.png` - The texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset for the sprite.
*   **offset\_y**: `2` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

### Animations:

#### `stand` Animation:

*   **name**: `"stand"`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `1` - Number of frames in the animation.
*   **frame\_width**: `2` - Width of each animation frame.
*   **frame\_height**: `4` - Height of each animation frame.
*   **frame\_wait**: `1` - Delay between frames.
*   **frames\_per\_row**: `8` - Number of frames per row in the sprite sheet.
*   **loop**: `1` - Whether the animation should loop.