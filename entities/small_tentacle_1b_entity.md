---
title: Small Tentacle 1b Entity
category: entities
---

# Small Tentacle 1b Entity

This document describes the `smalltentacle_1b.xml` entity, which defines a visual component for a small tentacle in Noita.

## Entity Definition

The core of this entity is the `<Entity>` tag.

## SpriteComponent

This component handles the visual representation of the tentacle.

### Key Attributes:

*   **`image_file`**: Specifies the texture file used for the sprite.
    *   `data/entities/verlet_chains/smalltentacle/smalltentacle_1b.png`
*   **`offset_x`**: The horizontal offset of the sprite.
    *   `0`
*   **`offset_y`**: The vertical offset of the sprite.
    *   `4.5`
*   **`update_transform`**: Determines if the sprite's transform (position, scale, rotation) should be updated.
    *   `0` (False)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   `0` (False)