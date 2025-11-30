---
title: Vine Part A3 Verlet Chain
category: entities
---

# Vine Part A3 Verlet Chain

This entity defines a single segment of a vine, specifically designed for use within Noita's verlet chain system. It primarily consists of a sprite component to visually represent the vine segment.

## Sprite Component

The `SpriteComponent` is responsible for rendering the visual appearance of the vine part.

### Key Attributes:

*   **`image_file`**: Specifies the XML file containing the sprite's visual data. In this case, it points to `data/entities/verlet_chains/vines/vine_parts/vine_a_3.xml`.
*   **`offset_x`**: The horizontal offset of the sprite from the entity's origin. Set to `0`.
*   **`offset_y`**: The vertical offset of the sprite from the entity's origin. Set to `1.5`.
*   **`update_transform`**: A flag indicating whether the sprite's transform (position, scale, rotation) should be updated automatically. Set to `0` (disabled).
*   **`update_transform_rotation`**: A flag indicating whether the sprite's rotation should be updated automatically. Set to `0` (disabled).

## Entity

The root element for this entity. It contains the `SpriteComponent` to define its visual properties.