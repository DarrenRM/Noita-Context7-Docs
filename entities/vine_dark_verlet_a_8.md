---
title: Vine Dark Verlet A 8
category: entities
---

# Vine Dark Verlet A 8

This entity defines a specific segment of a dark vine, designed for use in Noita'sverlet chain system.

## Sprite Component

The `SpriteComponent` handles the visual representation of this vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the sprite asset used for this vine segment. In this case, it points to `data/entities/verlet_chains/vines/vine_parts/vine_a_8.xml`.
*   **`offset_x`**: Horizontal offset for the sprite. Set to `0`.
*   **`offset_y`**: Vertical offset for the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, rotation, scale) is updated. Set to `0` (false), meaning it's static relative to its parent.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (false), meaning it's static.