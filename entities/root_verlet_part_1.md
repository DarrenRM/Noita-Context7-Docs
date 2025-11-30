---
title: Root Verlet Part 1
category: entities
---

# Root Verlet Part 1

This document describes the `root_verlet_1.xml` entity, which represents a segment of a root structure in Noita.

## Sprite Component

The `SpriteComponent` defines the visual appearance of this root part.

### Key Attributes:

*   **`image_file`**: Specifies the sprite to be used. In this case, it points to `data/entities/verlet_chains/root/root_parts/root_1.xml`.
*   **`offset_x`**: Horizontal offset for the sprite.
*   **`offset_y`**: Vertical offset for the sprite.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated. `0` indicates it is not.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. `0` indicates it is not.

```xml
<SpriteComponent 
  image_file="data/entities/verlet_chains/root/root_parts/root_1.xml" 
  offset_x="0"
  offset_y="3"
  update_transform="0"
  update_transform_rotation="0" >
</SpriteComponent>
```