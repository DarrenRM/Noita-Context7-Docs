---
title: Vine Part B5
category: entities
---

# Vine Part B5

This entity defines a specific segment of a vine, likely used in a "verlet chain" system for dynamic movement and physics.

## Sprite Component

This component handles the visual representation of the vine segment.

### Key Attributes:

*   **`image_file`**: `data/entities/verlet_chains/vines/vine_parts/vine_b_5.xml` - Specifies the image file used for this sprite.
*   **`offset_x`**: `0` - Horizontal offset of the sprite.
*   **`offset_y`**: `1.5` - Vertical offset of the sprite.
*   **`update_transform`**: `0` - Indicates that the sprite's transform (position, scale, rotation) is not updated by the engine's physics or update loop.
*   **`update_transform_rotation`**: `0` - Indicates that the sprite's rotation is not updated.