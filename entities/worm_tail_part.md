---
title: Worm Tail Part
category: entities
---

---

# Worm Tail Part

This document describes the `worm_part_tail.xml` entity, which defines a segment of a worm's body in Noita.

## SpriteComponent

This component handles the visual representation of the worm tail.

### Key Attributes:

*   **`image_file`**: Specifies the sprite image used for the tail segment.
    *   Value: `"data/entities/verlet_chains/worm/worm_parts/worm_tail.xml"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"6"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"6"`
*   **`update_transform`**: Determines if the sprite's transform (position, rotation, scale) should be updated.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   Value: `"0"` (Disabled)

## Entity

The root element for the worm tail part. It contains the `SpriteComponent`.