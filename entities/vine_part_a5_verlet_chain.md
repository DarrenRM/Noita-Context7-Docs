---
title: Vine Part A5 Verlet Chain
category: entities
---

# Vine Part A5 Verlet Chain

This document describes the `vine_verlet_a_5.xml` entity, which represents a segment of a vine in Noita'sverlet chain system.

## Sprite Component

The `SpriteComponent` defines the visual representation of this vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the sprite to be used. In this case, it points to `data/entities/verlet_chains/vines/vine_parts/vine_a_5.xml`.
*   **`offset_x`**: Horizontal offset for the sprite. Set to `0`.
*   **`offset_y`**: Vertical offset for the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, rotation, scale) is updated. Set to `0` (disabled).
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (disabled).

This entity is a simple visual component for a vine segment within a largerverlet chain structure.