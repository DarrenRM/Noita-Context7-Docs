---
title: Wraith Cape Part 4 Sprite
category: entities
---

---

# Wraith Cape Part 4 Sprite

This document describes the sprite data for a part of the Wraith Cape's storm animation in Noita.

## Sprite

The primary sprite for this cape part is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/wraith_cape/wraith_storm/parts/cape_4.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animations

The sprite includes a single animation named "stand".

### RectAnimation: "stand"

This animation defines how the sprite is displayed over time.

#### Key Attributes:

*   **name**: `"stand"` - The name of the animation.
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet.
*   **frame\_count**: `"1"` - The total number of frames in this animation.
*   **frame\_width**: `"11"` - The width of each individual frame.
*   **frame\_height**: `"24"` - The height of each individual frame.
*   **frame\_wait**: `"1"` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `"8"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop (1 for true, 0 for false).