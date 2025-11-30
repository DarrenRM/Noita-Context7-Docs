---
title: Cord Part A (5) Sprite
category: entities
---

# Cord Part A (5) Sprite

This document describes the sprite and animation data for a specific part of a cord entity in Noita.

## Sprite

The sprite defines the visual appearance of the cord part.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/cords/cord_parts/cord_a.png` - The texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default.

## Animation

This section defines the "stand" animation for the cord part.

### Key Attributes:

*   **name**: `stand` - The name of this animation.
*   **pos\_x**: `20` - The X-coordinate within the sprite sheet for the animation's starting frame.
*   **pos\_y**: `0` - The Y-coordinate within the sprite sheet for the animation's starting frame.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame.
*   **frame\_height**: `3` - The height of each individual frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).