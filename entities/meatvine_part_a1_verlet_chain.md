---
title: Meatvine Part A1 Verlet Chain
category: entities
---

# Meatvine Part A1 Verlet Chain

This document describes the `vine_verlet_a_1.xml` entity, which represents a segment of the meatvine's verlet chain.

## Sprite Component

The `SpriteComponent` defines the visual representation of this meatvine segment.

### Key Attributes:

*   **`image_file`**: Specifies the sprite image used for this part.
    *   Value: `"data/entities/verlet_chains/meatvine/vine_parts/vine_a_1.xml"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"0"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"1.5"`
*   **`update_transform`**: Controls whether the sprite's transform is updated.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated.
    *   Value: `"0"` (Disabled)