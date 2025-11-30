---
title: Monk Cape Verlet Chain Part 3
category: entities
---

---

# Monk Cape Verlet Chain Part 3

This document describes a component of the Monk Cape's verlet chain system in Noita, specifically `cape_verlet_3.xml`. It defines a visual sprite for a segment of the cape.

## SpriteComponent

This is the primary component, responsible for rendering the visual representation of this cape segment.

### Key Attributes:

*   **`image_file`**: Specifies the XML file that defines the sprite's appearance. In this case, it points to `data/entities/verlet_chains/monk_cape/parts/cape_3.xml`.
*   **`offset_x`**: The horizontal offset of the sprite from its entity's origin. Value: `1`.
*   **`offset_y`**: The vertical offset of the sprite from its entity's origin. Value: `12`.
*   **`z_index`**: Determines the rendering order of the sprite. Higher values are rendered on top. Value: `1.4`.
*   **`update_transform`**: Controls whether the sprite's transform (position, rotation, scale) is updated automatically. Value: `0` (disabled).
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated automatically. Value: `0` (disabled).