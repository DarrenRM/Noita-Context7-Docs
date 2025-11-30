---
title: Wraith Cape Part 1
category: entities
---

# Wraith Cape Part 1

This entity defines a single part of the Wraith's cape, specifically the first segment. It utilizes a `SpriteComponent` to render the visual appearance of the cape segment.

## SpriteComponent

This component handles the visual representation of the entity.

### Key Attributes:

*   **`image_file`**: Specifies the sprite sheet or XML file containing the visual data for the cape segment.
    *   Value: `"data/entities/verlet_chains/wraith_cape/wraith/parts/cape_1.xml"`
*   **`offset_x`**: The horizontal offset of the sprite from the entity's origin.
    *   Value: `"1"`
*   **`offset_y`**: The vertical offset of the sprite from the entity's origin.
    *   Value: `"12"`
*   **`z_index`**: Determines the rendering order of the sprite. Higher values are rendered on top.
    *   Value: `"1.2"`
*   **`update_transform`**: Controls whether the sprite's transform (position, rotation, scale) is updated automatically.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated automatically.
    *   Value: `"0"` (Disabled)