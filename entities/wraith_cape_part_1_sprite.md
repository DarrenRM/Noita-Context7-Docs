---
title: Wraith Cape Part 1 Sprite
category: entities
---

---

# Wraith Cape Part 1 Sprite

This document describes the sprite data for the first part of the Wraith Cape, used in the wraith storm effect.

## Sprite

The main sprite definition for this entity part.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/wraith_cape/wraith_storm/parts/cape_1.png` - The path to the sprite image file.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation: stand

Defines the "stand" animation for the sprite.

### Key Attributes:

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `"1"` - The total number of frames in this animation.
*   **frame\_width**: `"8"` - The width of each individual frame.
*   **frame\_height**: `"24"` - The height of each individual frame.
*   **frame\_wait**: `"1"` - The delay between frames (in game ticks).
*   **frames\_per\_row**: `"8"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Whether the animation should loop (1 for true, 0 for false).