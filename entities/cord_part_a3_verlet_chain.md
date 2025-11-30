---
title: Cord Part A3 Verlet Chain
category: entities
---

# Cord Part A3 Verlet Chain

This entity defines a single segment of a verlet chain, specifically designed for cords. It utilizes a sprite for visual representation.

## Sprite Component

The `SpriteComponent` defines the visual appearance and positioning of the cord segment.

### Key Attributes:

*   **`image_file`**: Specifies the image file used for the sprite. In this case, it points to `data/entities/verlet_chains/cords/cord_parts/cord_a_3.xml`.
*   **`offset_x`**: Horizontal offset for the sprite. Set to `0`.
*   **`offset_y`**: Vertical offset for the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform is updated. Set to `0` (disabled).
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (disabled).