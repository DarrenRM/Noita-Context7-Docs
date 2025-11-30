---
title: Vine Verlet 4 Entity
category: entities
---

# Vine Verlet 4 Entity

This document describes the `vine_verlet_4.xml` entity, a component likely used for visual representation of a centipede boss's segmented body or a similar vine-like structure in Noita.

## Sprite Component

The `SpriteComponent` defines the visual appearance and rendering properties of the entity.

### Key Attributes:

*   **`image_file`**: Specifies the texture file used for the sprite. In this case, it points to `data/entities/animals/boss_centipede/verlet_chains/verlet_4.xml`. This suggests a modular design where different parts of the centipede might use similarly named XML files for their sprites.
*   **`offset_x`**: Horizontal offset of the sprite from the entity's origin. Set to `0`.
*   **`offset_y`**: Vertical offset of the sprite from the entity's origin. Set to `3.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated automatically. Set to `0` (disabled).
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated automatically. Set to `0` (disabled).
*   **`z_index`**: Determines the rendering order of the sprite. A higher `z_index` means it will be drawn on top of other elements with lower `z_index`. Set to `1.1`.

## Entity Structure

The entity is a simple container for the `SpriteComponent`. This indicates that this specific entity's primary purpose is to display a visual element.

```xml
<Entity>
  <SpriteComponent
    image_file="data/entities/animals/boss_centipede/verlet_chains/verlet_4.xml"
    offset_x="0"
    offset_y="3.5"
    update_transform="0"
    update_transform_rotation="0"
    z_index="1.1"
  >
  </SpriteComponent>
</Entity>
```