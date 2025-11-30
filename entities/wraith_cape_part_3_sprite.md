---
title: Wraith Cape Part 3 Sprite
category: entities
---

# Wraith Cape Part 3 Sprite

This document describes the sprite data for a part of the Wraith Cape's storm animation in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/wraith_cape/wraith_storm/parts/cape_3.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - The horizontal offset of the sprite.
*   **offset\_y**: `0` - The vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is loaded.

## Animation

The sprite includes a single animation named "stand".

### RectAnimation: `stand`

This animation defines how the sprite is displayed over time.

#### Key Attributes:

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `0` - The starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `8` - The width of each individual animation frame.
*   **frame\_height**: `24` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).