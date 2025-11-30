---
title: Vine Part A2 Verlet Chain
category: entities
---

# Vine Part A2 Verlet Chain

This entity defines a single segment of a vine, specifically designed for use within Noita's verlet chain system. It primarily consists of a sprite component for visual representation.

## Sprite Component

The `SpriteComponent` dictates how this vine segment appears in the game.

### Key Attributes:

*   **`image_file`**: Specifies the sprite image to be used. In this case, it points to `data/entities/verlet_chains/vines/vine_parts/vine_a_2.xml`.
*   **`offset_x`**: Horizontal offset for the sprite. Set to `0`.
*   **`offset_y`**: Vertical offset for the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, rotation, scale) is updated. Set to `0` (disabled).
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (disabled).

This entity is a fundamental building block for creating dynamic vine structures in Noita.