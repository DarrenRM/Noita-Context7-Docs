---
title: Vine Part B3 Verlet Chain Entity
category: entities
---

# Vine Part B3 Verlet Chain Entity

This entity defines a segment of a vine, specifically part 'B3', designed for use in verlet chain physics.

## Key Components

### SpriteComponent
This component handles the visual representation of the vine segment.

*   **`image_file`**: Specifies the sprite to be used.
    *   `data/entities/verlet_chains/vines/vine_parts/vine_b_3.xml`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `0`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `1.5`
*   **`update_transform`**: Controls whether the sprite's transform is updated by physics.
    *   `0` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated by physics.
    *   `0` (Disabled)