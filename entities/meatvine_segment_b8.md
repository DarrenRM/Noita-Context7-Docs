---
title: Meatvine Segment B8
category: entities
---

# Meatvine Segment B8

This entity defines a segment of the meatvine's "verlet chain" structure, specifically a smaller, curved segment. It primarily consists of a sprite component to render its visual appearance.

## Sprite Component

This component dictates how the entity is visually represented.

### Key Attributes:

*   **`image_file`**: Specifies the sprite data for this vine segment.
    *   Value: `"data/entities/verlet_chains/meatvine/vine_parts/vine_b_8.xml"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"0"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"1.5"`
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated.
    *   Value: `"0"` (Disabled)