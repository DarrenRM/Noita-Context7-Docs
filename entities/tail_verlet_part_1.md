---
title: Tail Verlet Part 1
category: entities
---

# Tail Verlet Part 1

This entity defines a single segment of a "verlet chain" tail, likely used for creature appendages.

## SpriteComponent

This component handles the visual representation of the tail segment.

### Key Attributes:

*   **`image_file`**: Specifies the sprite to be used for this tail segment. In this case, it points to `data/entities/verlet_chains/tail/tail_1.xml`.
*   **`offset_x`**: Horizontal offset for the sprite.
*   **`offset_y`**: Vertical offset for the sprite.
*   **`update_transform`**: Controls whether the sprite's transform (position, rotation, scale) is updated. `0` indicates it is not automatically updated by the engine.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. `0` indicates it is not automatically updated.