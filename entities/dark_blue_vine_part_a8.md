---
title: Dark Blue Vine Part A8
category: entities
---

# Dark Blue Vine Part A8

This entity defines a single segment of a dark blue vine, specifically part A8. It is designed to be used within Noita'sverlet chain system for creating dynamic, growing vine structures.

## Key Components

### SpriteComponent
This component handles the visual representation of the vine segment.

*   **image_file**: `data/entities/verlet_chains/vines/vine_parts_blue/vine_a_8.xml` - Specifies the sprite asset used for this vine segment.
*   **offset_x**: `0` - Horizontal offset for the sprite.
*   **offset_y**: `1.5` - Vertical offset for the sprite.
*   **update_transform**: `0` - Disables automatic transform updates for the sprite.
*   **update_transform_rotation**: `0` - Disables automatic rotation updates for the sprite.

## Usage

This entity is intended to be part of a larger `verlet_chain` setup, where multiple such segments are linked together to form a complete vine. The `verlet_chain` component (not present in this snippet but implied by the file path) would manage the physics and connection of these segments.