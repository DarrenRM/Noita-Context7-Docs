---
title: Monk Cape Part 1 Sprite
category: entities
---

# Monk Cape Part 1 Sprite

This document describes the sprite data for the first part of the Monk's cape in Noita.

## Sprite

The main sprite for this cape part.

### Key Attributes

*   **filename**: `data/entities/verlet_chains/monk_cape/parts/cape_1.png` - The image file for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation to play by default.

## Animation: `stand`

Defines the "stand" animation for the cape part.

### Key Attributes

*   **name**: `stand` - The name of this animation.
*   **pos\_x**: `0` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `8` - The width of each individual frame.
*   **frame\_height**: `24` - The height of each individual frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).