---
title: Wraith Cape Part 2 Sprite
category: entities
---

# Wraith Cape Part 2 Sprite

This document describes the sprite data for the second part of the Wraith Cape's storm animation.

## Sprite

The primary sprite for this entity.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/wraith_cape/wraith_storm/parts/cape_2.png` - The path to the sprite image file.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

Defines the animations available for the sprite.

### `stand` Animation

This animation represents the standing pose of the cape part.

#### Key Attributes:

*   **name**: `"stand"` - The name of the animation.
*   **pos\_x**: `"0"` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos\_y**: `"0"` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame\_count**: `"1"` - The total number of frames in this animation.
*   **frame\_width**: `"8"` - The width of each individual frame.
*   **frame\_height**: `"24"` - The height of each individual frame.
*   **frame\_wait**: `"1"` - The duration each frame is displayed before advancing.
*   **frames\_per\_row**: `"8"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop (1 for true, 0 for false).