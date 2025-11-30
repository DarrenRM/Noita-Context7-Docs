---
title: Minion Tentacle Verlet 1 Sprite
category: entities
---

# Minion Tentacle Verlet 1 Sprite

This document describes the sprite component for the "Minion Tentacle Verlet 1" entity in Noita.

## SpriteComponent

This component defines the visual representation of the entity.

### Key Attributes:

*   **`image_file`**: Specifies the XML file containing the sprite's image data.
    *   Value: `"data/entities/animals/boss_centipede/verlet_chains/minion_tentacle_1.xml"`
*   **`offset_x`**: Horizontal offset of the sprite from the entity's origin.
    *   Value: `"0"`
*   **`offset_y`**: Vertical offset of the sprite from the entity's origin.
    *   Value: `"5.5"`
*   **`update_transform`**: Determines if the sprite's transform (position, scale, rotation) should be updated.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   Value: `"0"` (Disabled)
*   **`z_index`**: Controls the rendering order of the sprite. Higher values are rendered on top.
    *   Value: `"1.1"`