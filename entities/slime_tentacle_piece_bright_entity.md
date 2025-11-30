---
title: Slime Tentacle Piece (Bright) Entity
category: entities
---

# Slime Tentacle Piece (Bright) Entity

This document describes the `slime_tentacle_piece_bright.xml` entity, which represents a single segment of a bright slime tentacle in Noita.

## Sprite Component

The `SpriteComponent` defines the visual appearance of the entity.

### Key Attributes:

*   **`image_file`**: Specifies the texture file used for the sprite.
    *   `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_bright.png`
*   **`offset_x`**: Horizontal offset of the sprite.
    *   `0`
*   **`offset_y`**: Vertical offset of the sprite.
    *   `1`
*   **`update_transform`**: Determines if the sprite's transform (position, rotation, scale) should be updated.
    *   `0` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   `0` (Disabled)

## Entity Structure

This entity is a basic component, primarily defined by its visual representation through the `SpriteComponent`. It does not contain other complex components like physics, AI, or damage. This suggests it's likely a visual element used within a larger, more complex entity (e.g., a slime tentacle that is constructed from multiple such pieces).