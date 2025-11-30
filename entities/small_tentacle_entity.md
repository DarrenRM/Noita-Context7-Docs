---
title: Small Tentacle Entity
category: entities
---

# Small Tentacle Entity

This document describes the `smalltentacle_1.xml` entity, which defines a small tentacle object within Noita.

## Entity Definition

The core of the entity is defined by the `<Entity>` tag.

## Sprite Component

The `<SpriteComponent>` defines the visual representation of the tentacle.

### Key Attributes:

*   **`image_file`**: Specifies the texture file used for the sprite.
    *   Value: `"data/entities/verlet_chains/smalltentacle/smalltentacle_1.png"`
*   **`offset_x`**: The horizontal offset of the sprite from the entity's origin.
    *   Value: `"0"`
*   **`offset_y`**: The vertical offset of the sprite from the entity's origin.
    *   Value: `"4.5"`
*   **`update_transform`**: Determines if the sprite's transform (position, rotation, scale) should be updated.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   Value: `"0"` (Disabled)