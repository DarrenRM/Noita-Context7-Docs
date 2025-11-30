---
title: Tentacle Verlet 1 Entity
category: entities
---

# Tentacle Verlet 1 Entity

This document describes the `tentacle_verlet_1.xml` entity, which appears to be a visual component for a tentacle in Noita.

## Sprite Component

The primary component of this entity is `SpriteComponent`, which defines its visual representation.

### Key Attributes:

*   **`image_file`**: Specifies the sprite asset to be used. In this case, it points to `data/entities/animals/parallel/tentacles/tentacle_1.xml`. This suggests that `tentacle_verlet_1.xml` is likely a visual variant or a specific state of the `tentacle_1.xml` entity.
*   **`offset_x`**: Horizontal offset of the sprite.
*   **`offset_y`**: Vertical offset of the sprite.
*   **`update_transform`**: Controls whether the sprite's transform (position, rotation, scale) is updated by the game engine. `0` indicates it is not automatically updated.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. `0` indicates it is not automatically updated.
*   **`z_index`**: Determines the rendering order of the sprite. A higher value means it will be rendered on top of other elements with lower `z_index`.