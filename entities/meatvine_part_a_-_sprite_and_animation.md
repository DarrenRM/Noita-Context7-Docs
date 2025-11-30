---
title: Meatvine Part A - Sprite and Animation
category: entities
---

# Meatvine Part A - Sprite and Animation

This document describes the sprite and animation data for a specific part of the "meatvine" entity in Noita.

## Sprite

The `Sprite` element defines the visual appearance of the entity part.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/meatvine/vine_parts/vine_a.png` - The texture file used for this sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default when the entity is spawned.

## Animation

The `RectAnimation` element defines a rectangular animation sequence.

### Key Attributes:

*   **name**: `stand` - The name of this animation, referenced by `default_animation`.
*   **pos\_x**: `28` - The X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual animation frame.
*   **frame\_height**: `3` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).