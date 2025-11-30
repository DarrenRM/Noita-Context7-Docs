---
title: Slime Vine Verlet Part 2
category: entities
---

# Slime Vine Verlet Part 2

This document describes the XML configuration for a specific part of the "slime vine"verlet chain entity in Noita.

## Entity Definition

The core of this file defines an entity with a `SpriteComponent`.

### SpriteComponent

This component handles the visual representation of the entity.

*   **`image_file`**: Specifies the sprite image to be used.
    *   Value: `data/entities/verlet_chains/slime_vine/parts/slime_vine_2.xml`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `0`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `1.5`
*   **`update_transform`**: Determines if the sprite's transform (position, scale, rotation) should be updated.
    *   Value: `0` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   Value: `0` (Disabled)