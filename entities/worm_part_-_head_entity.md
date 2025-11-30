---
title: Worm Part - Head Entity
category: entities
---

# Worm Part - Head Entity

This document describes the `worm_part_head.xml` entity, which defines the visual and functional aspects of a worm's head segment in Noita.

## Key Components

### SpriteComponent

This component handles the visual representation of the worm's head.

*   **`image_file`**: Specifies the sprite asset used for the worm head.
    *   Value: `data/entities/verlet_chains/worm/worm_parts/worm_head.xml`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `6`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `6`
*   **`update_transform`**: Determines if the sprite's transform (position, scale) should be updated.
    *   Value: `0` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   Value: `0` (Disabled)