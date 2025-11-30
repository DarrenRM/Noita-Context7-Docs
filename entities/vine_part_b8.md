---
title: Vine Part B8
category: entities
---

# Vine Part B8

This entity defines a specific segment of a vine, likely used in a "verlet chain" system for dynamic movement and physics.

## Sprite Component

This component handles the visual representation of the vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the sprite asset used for this vine part.
    *   `data/entities/verlet_chains/vines/vine_parts/vine_b_8.xml`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `0`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `1.5`
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated.
    *   `0` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated.
    *   `0` (Disabled)