---
title: Worm Body Part Entity
category: entities
---

# Worm Body Part Entity

This document describes the `worm_part_body.xml` entity, which defines a single segment of a worm in Noita.

## SpriteComponent

This component handles the visual representation of the worm body part.

### Key Attributes:

*   **`image_file`**: Specifies the sprite image used for the worm body.
    *   Value: `"data/entities/verlet_chains/worm/worm_parts/worm_body.xml"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"6"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"6"`
*   **`update_transform`**: Controls whether the sprite's transform is updated.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated.
    *   Value: `"0"` (Disabled)