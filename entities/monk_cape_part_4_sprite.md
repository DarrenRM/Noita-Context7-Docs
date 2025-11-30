---
title: Monk Cape Part 4 Sprite
category: entities
---

# Monk Cape Part 4 Sprite

This document describes the sprite data for a part of the Monk Cape entity in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual representation of this cape part.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/monk_cape/parts/cape_4.png` - The path to the sprite image file.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation: "stand"

The `<RectAnimation>` element defines the "stand" animation for this sprite.

### Key Attributes:

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `11` - The width of each individual frame.
*   **frame\_height**: `24` - The height of each individual frame.
*   **frame\_wait**: `1` - The number of game ticks to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).