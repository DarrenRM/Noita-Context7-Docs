---
title: Minion Tentacle Verlet 2 Entity
category: entities
---

# Minion Tentacle Verlet 2 Entity

This document describes the `minion_tentacle_verlet_2.xml` entity, a component likely used in the creation of tentacle-like enemies or environmental hazards in Noita.

## Key Components

### SpriteComponent

This component defines the visual representation of the entity.

*   **`image_file`**: `data/entities/animals/special/verlet_chains/minion_tentacle_2.xml` - Specifies the sprite asset used for this entity.
*   **`offset_x`**: `0` - Horizontal offset for the sprite.
*   **`offset_y`**: `5.5` - Vertical offset for the sprite.
*   **`update_transform`**: `0` - Indicates that the sprite's transform (position, rotation, scale) is not automatically updated by the engine.
*   **`update_transform_rotation`**: `0` - Indicates that the sprite's rotation is not automatically updated.
*   **`z_index`**: `1.1` - Controls the rendering order of the sprite, with higher values appearing in front.

```xml
<SpriteComponent 
  image_file="data/entities/animals/special/verlet_chains/minion_tentacle_2.xml" 
  offset_x="0"
  offset_y="5.5"
  update_transform="0"
  update_transform_rotation="0"
  z_index="1.1"
>
</SpriteComponent>
```