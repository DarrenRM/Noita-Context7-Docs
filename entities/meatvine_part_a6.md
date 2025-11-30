---
title: Meatvine Part A6
category: entities
---

# Meatvine Part A6

This entity defines a specific segment of the meatvine's "verlet chain" structure, responsible for its visual representation.

## Sprite Component

The `SpriteComponent` dictates how this entity is rendered.

### Key Attributes:

*   **`image_file`**: Specifies the graphical asset used for this vine segment.
    *   `data/entities/verlet_chains/meatvine/vine_parts/vine_a_6.xml`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `0`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `1.5`
*   **`update_transform`**: Controls whether the sprite's transform (position, rotation, scale) is updated.
    *   `0` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated.
    *   `0` (Disabled)