---
title: Tentacle Verlet 4 Entity
category: entities
---

---

# Tentacle Verlet 4 Entity

This document describes the `tentacle_verlet_4.xml` entity, which appears to be a visual component for a tentacle-like creature in Noita.

## SpriteComponent

This is the primary component defining the visual representation of the entity.

### Key Attributes:

*   **`image_file`**: Specifies the sprite asset to be used. In this case, it points to `data/entities/animals/parallel/tentacles/tentacle_4.xml`. This suggests that `tentacle_verlet_4.xml` is likely a variant or a specific state of a more general tentacle entity defined in `tentacle_4.xml`.
*   **`offset_x`**: Horizontal offset of the sprite. Value is `0`.
*   **`offset_y`**: Vertical offset of the sprite. Value is `5.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, rotation, scale) is updated. Value is `0` (false), meaning it's likely static or controlled by other means.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Value is `0` (false), indicating a fixed orientation.
*   **`z_index`**: Determines the drawing order of the sprite. Value is `1.1`, placing it above other elements with lower z-indices.

## Entity

The root element for the entity definition. It contains the `SpriteComponent`.

### Key Elements:

*   **`<Entity>`**: The main container for entity definitions.
*   **`<SpriteComponent>`**: Defines the visual aspects of the entity.

This entity appears to be a simple visual element, likely used in conjunction with other components or scripts to create a dynamic tentacle animation or behavior. The `verlet` in its filename might suggest a state related to being damaged or a specific animation phase.