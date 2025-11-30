---
title: Cord Part A5 Verlet Chain
category: entities
---

# Cord Part A5 Verlet Chain

This document describes the `cord_verlet_a_5.xml` entity, which represents a segment of a Verlet chain, specifically a cord part.

## Sprite Component

The `SpriteComponent` defines the visual representation of this entity.

### Key Attributes:

*   **`image_file`**: Specifies the sprite image to be used. In this case, it points to `data/entities/verlet_chains/cords/cord_parts/cord_a_5.xml`.
*   **`offset_x`**: Horizontal offset for the sprite. Set to `0`.
*   **`offset_y`**: Vertical offset for the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform is updated. Set to `0` (disabled).
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (disabled).

## Entity Structure

This entity primarily consists of a `SpriteComponent`. It is designed to be part of a larger Verlet chain system, likely for physics-based rope or chain simulations. The `update_transform` and `update_transform_rotation` being disabled suggests that its position and rotation are managed by the Verlet chain logic rather than directly by this entity's component.