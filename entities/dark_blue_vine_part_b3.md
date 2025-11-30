---
title: Dark Blue Vine Part B3
category: entities
---

---

# Dark Blue Vine Part B3

This entity represents a single segment of a dark blue vine, specifically part B3. It is designed to be used within Noita'sverlet chain system for creating dynamic vine structures.

## Key Components

### SpriteComponent
This component defines the visual representation of the vine segment.

*   **image_file**: `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_b_3.xml` - Specifies the sprite asset used for this vine part.
*   **offset_x**: `0` - Horizontal offset for the sprite.
*   **offset_y**: `1.5` - Vertical offset for the sprite.
*   **update_transform**: `0` - Disables automatic transform updates for the sprite.
*   **update_transform_rotation**: `0` - Disables automatic rotation updates for the sprite.

## Usage

This entity is intended to be part of a larger `verlet_chain` structure, where multiple vine parts are linked together to form a flexible, physics-driven vine. The `SpriteComponent` is configured to use a specific sprite file and has minimal transform updates, suggesting it relies on theverlet chain's physics for its movement and positioning.