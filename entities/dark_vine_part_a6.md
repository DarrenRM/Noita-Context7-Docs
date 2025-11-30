---
title: Dark Vine Part A6
category: entities
---

# Dark Vine Part A6

This entity defines a single segment of a dark vine, specifically part 'A6'. It is designed to be used within a `verlet_chain` to create dynamic, flexible vine structures.

## Sprite Component

The `SpriteComponent` handles the visual representation of this vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the sprite asset used for this vine segment.
    *   `data/entities/verlet_chains/vines/vine_parts/vine_dark_a_6.xml`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `0`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `1.5`
*   **`update_transform`**: Controls whether the sprite's transform is updated.
    *   `0` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated.
    *   `0` (Disabled)