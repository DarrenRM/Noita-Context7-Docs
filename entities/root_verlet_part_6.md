---
title: Root Verlet Part 6
category: entities
---

# Root Verlet Part 6

This entity defines a specific part of a "root"verlet chain, likely used for environmental elements or enemy structures in Noita.

## Sprite Component

The `SpriteComponent` defines the visual representation of this entity.

### Key Attributes:

*   **`image_file`**: Specifies the image file used for the sprite. In this case, it points to `data/entities/verlet_chains/root/root_parts/root_6.xml`. This suggests a modular approach where different parts of the root are defined by separate XML files.
*   **`offset_x`**: Horizontal offset of the sprite.
*   **`offset_y`**: Vertical offset of the sprite.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated. `0` indicates it is not.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. `0` indicates it is not.

This configuration suggests that `root_verlet_6` is a static visual element within a larger verlet chain structure.