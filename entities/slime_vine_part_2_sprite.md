---
title: Slime Vine Part 2 Sprite
category: entities
---

# Slime Vine Part 2 Sprite

This document describes the sprite data for a segment of the slime vine entity in Noita.

## Sprite

The primary sprite for this entity segment is defined by the `<Sprite>` tag.

### Key Attributes

*   **filename**: `data/entities/verlet_chains/slime_vine/parts/slime_vine_2.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - The horizontal offset of the sprite.
*   **offset\_y**: `0` - The vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default when the entity is active.

## Animations

The entity utilizes a single animation named "stand".

### RectAnimation: "stand"

This animation defines the visual frames for the slime vine segment.

#### Key Attributes

*   **name**: `stand` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `5` - The width of each individual animation frame.
*   **frame\_height**: `3` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before transitioning.
*   **frames\_per\_row**: `8` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation will loop continuously.