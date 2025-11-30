---
title: Blue Vine Part A7 Verlet Chain
category: entities
---

# Blue Vine Part A7 Verlet Chain

This document describes the `vine_verlet_a_7.xml` entity, which represents a segment of a blue vine in Noita. It's designed for use within verlet chains, allowing for dynamic and flexible vine structures.

## Sprite Component

The `SpriteComponent` defines the visual representation of this vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the sprite's image source.
    *   `data/entities/verlet_chains/vines/vine_parts_blue/vine_a_7.xml`
*   **`offset_x`**: Horizontal offset of the sprite.
    *   `0`
*   **`offset_y`**: Vertical offset of the sprite.
    *   `1.5`
*   **`update_transform`**: Controls whether the sprite's transform is updated.
    *   `0` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated.
    *   `0` (Disabled)

## Entity Structure

This entity primarily consists of a `SpriteComponent`, indicating it's a visual element designed to be part of a larger, dynamically simulated structure (a verlet chain). No other components are present, suggesting its behavior and interaction are managed by the verlet chain system it belongs to.