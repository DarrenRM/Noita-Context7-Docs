---
title: Vine Verlet 1 Entity
category: entities
---

# Vine Verlet 1 Entity

This document describes the `vine_verlet_1.xml` entity, which appears to be a visual component for a boss centipede's "verlet chains" in Noita.

## Sprite Component

The primary component of this entity is `SpriteComponent`, responsible for its visual representation.

### Key Attributes:

*   **`image_file`**: `data/entities/animals/boss_centipede/verlet_chains/verlet_1.xml`
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