---
title: Vine Part A5 Sprite
category: entities
---

# Vine Part A5 Sprite

This document describes the sprite and animation data for a specific part of a vine entity in Noita.

## Sprite

The primary sprite for this vine part is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts/vine_a.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `0` - The horizontal offset of the sprite.
*   **offset\_y**: `0` - The vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default when the entity is created.

## Animation: `stand`

The `stand` animation defines how the sprite is displayed over time.

### Key Attributes:

*   **name**: `stand` - The identifier for this animation.
*   **pos\_x**: `16` - The starting X-coordinate within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - The starting Y-coordinate within the sprite sheet for the animation frames.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual animation frame.
*   **frame\_height**: `3` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.