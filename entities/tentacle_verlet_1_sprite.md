---
title: Tentacle Verlet 1 Sprite
category: entities
---

# Tentacle Verlet 1 Sprite

This document describes the sprite component for the `tentacle_verlet_1` entity in Noita.

## SpriteComponent

This component defines the visual representation of the entity.

### Key Attributes:

*   **`image_file`**: Specifies the path to the sprite's image file.
    *   Value: `"data/entities/animals/boss_pit/tentacle_1.xml"`
*   **`offset_x`**: The horizontal offset of the sprite from the entity's origin.
    *   Value: `"0"`
*   **`offset_y`**: The vertical offset of the sprite from the entity's origin.
    *   Value: `"5.5"`
*   **`update_transform`**: Determines if the sprite's transform (position, scale, rotation) should be updated automatically.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated automatically.
    *   Value: `"0"` (Disabled)
*   **`z_index`**: Controls the drawing order of the sprite. Higher values are drawn on top.
    *   Value: `"1.1"`