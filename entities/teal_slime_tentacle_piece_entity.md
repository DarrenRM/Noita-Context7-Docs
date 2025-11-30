---
title: Teal Slime Tentacle Piece Entity
category: entities
---

# Teal Slime Tentacle Piece Entity

This document describes the `tealslime_tentacle_piece.xml` entity, which represents a single segment of the Teal Slime's tentacle in Noita.

## Sprite Component

The `SpriteComponent` defines the visual representation of the tentacle piece.

### Key Attributes:

*   **`image_file`**: Specifies the texture file used for the tentacle piece.
    *   Value: `"data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece.png"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"0"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"1"`
*   **`update_transform`**: Determines if the sprite's transform (position, scale, rotation) should be updated.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   Value: `"0"` (Disabled)