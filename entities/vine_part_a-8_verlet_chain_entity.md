---
title: Vine Part A-8 Verlet Chain Entity
category: entities
---

# Vine Part A-8 Verlet Chain Entity

This document describes the `vine_verlet_a_8.xml` entity, which represents a segment of a vine in Noita's verlet chain system.

## Sprite Component

The `SpriteComponent` defines the visual representation of this vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the sprite to be used for this vine part.
    *   Value: `"data/entities/verlet_chains/vines/vine_parts/vine_a_8.xml"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"0"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"1.5"`
*   **`update_transform`**: Determines if the sprite's transform (position, rotation, scale) should be updated.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   Value: `"0"` (Disabled)