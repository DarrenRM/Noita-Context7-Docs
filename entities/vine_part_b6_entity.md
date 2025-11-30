---
title: Vine Part B6 Entity
category: entities
---

# Vine Part B6 Entity

This document describes the `vine_verlet_b_6.xml` entity, which represents a segment of a vine in Noita.

## Sprite Component

The `SpriteComponent` defines the visual appearance of this vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the sprite image used for this vine part.
    *   Value: `data/entities/verlet_chains/vines/vine_parts/vine_b_6.xml`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `0`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `1.5`
*   **`update_transform`**: Determines if the sprite's transform (position, rotation, scale) should be updated.
    *   Value: `0` (False - transform is static)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   Value: `0` (False - rotation is static)