---
title: Minion Tentacle Verlet 4 Entity
category: entities
---

---

# Minion Tentacle Verlet 4 Entity

This document describes the `minion_tentacle_verlet_4.xml` entity, a component likely used in the Noita game for creating tentacle-like visual elements.

## Sprite Component

The primary visual representation of this entity is defined by its `SpriteComponent`.

### Key Attributes:

*   **`image_file`**: `data/entities/animals/special/verlet_chains/minion_tentacle_4.xml`
    *   Specifies the image file used for the sprite. This indicates it's part of a larger tentacle animation or asset set.
*   **`offset_x`**: `0`
    *   Horizontal offset for the sprite.
*   **`offset_y`**: `5.5`
    *   Vertical offset for the sprite.
*   **`update_transform`**: `0`
    *   Disables automatic transform updates for the sprite.
*   **`update_transform_rotation`**: `0`
    *   Disables automatic rotation updates for the sprite.
*   **`z_index`**: `1.1`
    *   Determines the rendering order of the sprite. A higher `z_index` means it will be drawn on top of other elements with lower `z_index` values.

## Entity Structure

The entity is a simple container for its `SpriteComponent`, suggesting it's a visual-only element or relies on other entities/scripts for its behavior and animation.