---
title: Cord Verlet A 1
category: entities
---

# Cord Verlet A 1

This entity defines a single segment of a Verlet chain, specifically a type of cord. It primarily uses a `SpriteComponent` to render its visual appearance.

## SpriteComponent

This component handles the visual representation of the entity.

### Key Attributes:

*   **`image_file`**: Specifies the image file used for the sprite. In this case, it points to `data/entities/verlet_chains/cords/cord_parts/cord_a_1.xml`. This suggests a modular approach where different cord segments might have slightly varied sprites.
*   **`offset_x`**: Horizontal offset for the sprite. Set to `0`.
*   **`offset_y`**: Vertical offset for the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated. Set to `0` (false), meaning its position is likely managed by the Verlet chain logic rather than direct transform updates.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (false), indicating rotation is also handled by the Verlet chain.

## Entity

The root element for this entity. It contains the `SpriteComponent`.

### Key Elements:

*   **`<SpriteComponent>`**: As detailed above, this is the primary component defining the visual aspect of the cord segment.

This entity is a fundamental building block for creating rope-like structures within Noita using the Verlet chain system. Its simplicity suggests that the complex physics and behavior of the cord are managed by other, external systems that utilize these segments.