---
title: Tentacle Verlet 3 Entity
category: entities
---

# Tentacle Verlet 3 Entity

This document describes the `tentacle_verlet_3.xml` entity, which appears to be a visual component for a tentacle in Noita.

## Sprite Component

The primary component for this entity is `SpriteComponent`, which defines its visual representation.

### Key Attributes:

*   **`image_file`**: Specifies the sprite asset used. In this case, it points to `data/entities/animals/parallel/tentacles/tentacle_3.xml`. This suggests that `tentacle_verlet_3.xml` is likely a visual variant or a specific state of the `tentacle_3.xml` entity.
*   **`offset_x`**: Horizontal offset of the sprite. Set to `0`.
*   **`offset_y`**: Vertical offset of the sprite. Set to `5.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, rotation, scale) is updated. Set to `0` (false), meaning it's static relative to its parent entity.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (false), meaning it maintains a fixed rotation.
*   **`z_index`**: Determines the drawing order of the sprite. Set to `1.1`. Higher values are drawn on top.

This entity appears to be a simple visual element, likely used in conjunction with other entities to form a complete tentacle creature or effect. Its static nature suggests it's a fixed part of a larger animated or interactive entity.