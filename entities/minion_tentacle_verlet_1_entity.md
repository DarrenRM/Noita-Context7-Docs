---
title: Minion Tentacle Verlet 1 Entity
category: entities
---

---

# Minion Tentacle Verlet 1 Entity

This document describes the `minion_tentacle_verlet_1.xml` entity, a component likely used for a tentacle-like creature in Noita.

## Key Components

### SpriteComponent

This component defines the visual representation of the entity.

*   **`image_file`**: `data/entities/animals/special/verlet_chains/minion_tentacle_1.xml` - Specifies the sprite asset used for the tentacle.
*   **`offset_x`**: `0` - Horizontal offset for the sprite.
*   **`offset_y`**: `5.5` - Vertical offset for the sprite.
*   **`update_transform`**: `0` - Indicates that the sprite's transform (position, scale, rotation) is not automatically updated by the engine.
*   **`update_transform_rotation`**: `0` - Indicates that the sprite's rotation is not automatically updated.
*   **`z_index`**: `1.1` - Controls the rendering order of the sprite, with higher values appearing in front.

```xml
<Entity>
  <SpriteComponent
    image_file="data/entities/animals/special/verlet_chains/minion_tentacle_1.xml"
    offset_x="0"
    offset_y="5.5"
    update_transform="0"
    update_transform_rotation="0"
    z_index="1.1"
  />
</Entity>