---
title: Vine Part B1 Verlet Chain
category: entities
---

# Vine Part B1 Verlet Chain

This entity defines a single segment of a verlet chain, specifically a vine segment. It primarily uses a sprite to visually represent the vine part.

## Sprite Component

This component handles the visual representation of the vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the sprite image to be used.
    *   `data/entities/verlet_chains/vines/vine_parts/vine_b_1.xml`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `0`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `1.5`
*   **`update_transform`**: Determines if the sprite's transform (position, scale, rotation) should be updated.
    *   `0` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   `0` (Disabled)