---
title: Small Tentacle 2 Entity
category: entities
---

# Small Tentacle 2 Entity

This document describes the `smalltentacle_2.xml` entity, which defines a visual component for a small tentacle in Noita.

## Entity Definition

The core of this entity is the `<Entity>` tag.

## SpriteComponent

This component defines the visual representation of the entity.

### Key Attributes:

*   **`image_file`**: Specifies the texture file used for the sprite.
    *   Value: `"data/entities/verlet_chains/smalltentacle/smalltentacle_2.png"`
*   **`offset_x`**: The horizontal offset of the sprite from its origin.
    *   Value: `"0"`
*   **`offset_y`**: The vertical offset of the sprite from its origin.
    *   Value: `"4.5"`
*   **`update_transform`**: Determines if the sprite's transform (position, scale, rotation) should be updated.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   Value: `"0"` (Disabled)