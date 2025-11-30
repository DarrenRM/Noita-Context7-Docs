---
title: Debug Rope Entity
category: entities
---

# Debug Rope Entity

This document describes the `rope2.xml` entity, a debug asset likely used for visual testing or development within Noita.

## Entity Definition

The core of this entity is its `SpriteComponent`, which defines its visual representation.

### SpriteComponent

This component handles the rendering of the entity.

*   **`image_file`**: `data/entities/debug/rope2.png`
    *   Specifies the texture file used for the sprite.
*   **`offset_x`**: `0`
    *   Horizontal offset for the sprite's position.
*   **`offset_y`**: `2`
    *   Vertical offset for the sprite's position.
*   **`update_transform`**: `0`
    *   Indicates whether the sprite's transform (position, scale, rotation) should be updated automatically. `0` means it's static.
*   **`update_transform_rotation`**: `0`
    *   Indicates whether the sprite's rotation should be updated automatically. `0` means it's static.

This entity is very basic, primarily serving as a visual placeholder or debug tool. It lacks any physics, collision, or functional components.