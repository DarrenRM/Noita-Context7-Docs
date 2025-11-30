---
title: Blue Vine Part A3 Verlet Chain
category: entities
---

# Blue Vine Part A3 Verlet Chain

This entity defines a single segment of a blue vine, specifically designed for use inverlet chains. Verlet chains are a physics simulation technique used to create flexible, chain-like structures.

## SpriteComponent

This component handles the visual representation of the vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the sprite asset used for this vine segment.
    *   Value: `"data/entities/verlet_chains/vines/vine_parts_blue/vine_a_3.xml"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"0"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"1.5"`
*   **`update_transform`**: Determines if the sprite's transform (position, rotation, scale) should be updated by the physics system.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated by the physics system.
    *   Value: `"0"` (Disabled)