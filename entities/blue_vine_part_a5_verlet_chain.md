---
title: Blue Vine Part A5 Verlet Chain
category: entities
---

# Blue Vine Part A5 Verlet Chain

This document describes the `vine_verlet_a_5.xml` entity, which represents a segment of a blue vine in Noita. It's part of a verlet chain, meaning it's designed to connect and animate dynamically with other vine segments.

## Sprite Component

The `SpriteComponent` defines the visual appearance and positioning of this vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the sprite asset used for this vine part.
    *   Value: `"data/entities/verlet_chains/vines/vine_parts_blue/vine_a_5.xml"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"0"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"1.5"`
*   **`update_transform`**: Determines if the sprite's transform (position, rotation, scale) should be updated by the game engine.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Determines if the sprite's rotation should be updated.
    *   Value: `"0"` (Disabled)

## Entity Structure

This entity primarily consists of a `SpriteComponent`. It's designed to be part of a larger verlet chain, implying other components (like physics or connection logic) are handled by the system that instantiates and manages these verlet chain entities.