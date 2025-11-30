---
title: Vine Verlet 3 Entity
category: entities
---

# Vine Verlet 3 Entity

This document describes the `vine_verlet_3.xml` entity, which appears to be a visual component for a boss centipede's "verlet chains" in Noita.

## Sprite Component

The primary component is `SpriteComponent`, defining the visual representation of this entity.

### Key Attributes:

*   **`image_file`**: `data/entities/animals/boss_centipede/verlet_chains/verlet_3.xml`
    *   Specifies the image file used for the sprite.
*   **`offset_x`**: `0`
    *   Horizontal offset for the sprite.
*   **`offset_y`**: `3.5`
    *   Vertical offset for the sprite.
*   **`update_transform`**: `0`
    *   Disables automatic transform updates.
*   **`update_transform_rotation`**: `0`
    *   Disables automatic rotation updates.
*   **`z_index`**: `1.1`
    *   Determines the rendering order of the sprite. Higher values are rendered on top.