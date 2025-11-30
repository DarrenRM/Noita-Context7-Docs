---
title: Dark Blue Vine Part B-8 Entity
category: entities
---

# Dark Blue Vine Part B-8 Entity

This document describes the entity configuration for a specific part of a dark blue vine in Noita, designed for AI-assisted modding.

## Entity Configuration

This entity defines a single segment of a dark blue vine.

### Key Components

*   **SpriteComponent**: This component handles the visual representation of the vine segment.
    *   `image_file`: Specifies the sprite to be used. In this case, it points to `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_b_8.xml`.
    *   `offset_x`: Horizontal offset for the sprite. Set to `0`.
    *   `offset_y`: Vertical offset for the sprite. Set to `1.5`.
    *   `update_transform`: Controls whether the sprite's transform is updated. Set to `0` (disabled).
    *   `update_transform_rotation`: Controls whether the sprite's rotation is updated. Set to `0` (disabled).