---
title: Vine Part A3 Sprite
category: entities
---

# Vine Part A3 Sprite

This document describes the sprite and animation data for `vine_a_3.xml`, a component of the vine entity in Noita.

## Sprite

The primary sprite for this vine part is defined by the `<Sprite>` tag.

### Key Attributes

*   **filename**: `data/entities/verlet_chains/vines/vine_parts/vine_a.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default when the entity is spawned.

## Animation

The entity utilizes a single animation named "stand".

### Key Attributes

*   **name**: `stand` - The identifier for this animation.
*   **pos\_x**: `8` - The X-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual animation frame.
*   **frame\_height**: `3` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop indefinitely.