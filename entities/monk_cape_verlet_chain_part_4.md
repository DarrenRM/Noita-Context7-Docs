---
title: Monk Cape Verlet Chain Part 4
category: entities
---

# Monk Cape Verlet Chain Part 4

This document describes a specific part of the monk's capeverlet chain, identified as `cape_verlet_4.xml`. This entity primarily defines the visual representation of a segment of the cape.

## Sprite Component

The `SpriteComponent` is the core element, defining how this part of the cape is rendered.

### Key Attributes:

*   **`image_file`**: Specifies the image file used for the sprite. In this case, it points to `data/entities/verlet_chains/monk_cape/parts/cape_4.xml`. This likely contains the actual sprite data or a reference to it.
*   **`offset_x`**: The horizontal offset of the sprite from its origin. Set to `1`.
*   **`offset_y`**: The vertical offset of the sprite from its origin. Set to `12`.
*   **`z_index`**: Determines the rendering order of the sprite. A `z_index` of `1.5` suggests it will be rendered above or behind other elements depending on their own `z_index` values.
*   **`update_transform`**: A flag indicating whether the sprite's transform (position, scale, rotation) should be updated. Set to `0`, meaning it's static in terms of transform updates.
*   **`update_transform_rotation`**: A flag indicating whether the sprite's rotation should be updated. Set to `0`, meaning its rotation is also static.

## Entity Structure

The entity is a simple container for the `SpriteComponent`. There are no other components or complex logic defined within this specific XML file. This suggests that the behavior and physics of the cape are handled by other related entities or systems within the game.