---
title: Cord A Part 2 Sprite
category: entities
---

# Cord A Part 2 Sprite

This document describes the sprite data for a component of a Verlet chain cord, specifically `cord_a_2.xml`.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes

*   **filename**: `data/entities/verlet_chains/cords/cord_parts/cord_a.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - The horizontal offset of the sprite.
*   **offset\_y**: `0` - The vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default.

## Animation

The sprite utilizes a single animation named "stand".

### Key Attributes

*   **name**: `stand` - The name of the animation.
*   **pos\_x**: `4` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual animation frame.
*   **frame\_height**: `3` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).