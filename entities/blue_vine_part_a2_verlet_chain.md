---
title: Blue Vine Part A2 Verlet Chain
category: entities
---

---

# Blue Vine Part A2 Verlet Chain

This document describes the `vine_verlet_a_2.xml` entity, which represents a segment of a blue vine in Noita. It's a component of a larger verlet chain system used for dynamic, flexible objects.

## Sprite Component

The `SpriteComponent` defines the visual representation of this vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the sprite's image. In this case, it points to `data/entities/verlet_chains/vines/vine_parts_blue/vine_a_2.xml`. This indicates that the visual asset for this specific vine segment is defined in a separate XML file, likely containing animation or frame data.
*   **`offset_x`**: Horizontal offset of the sprite from the entity's origin. Set to `0`.
*   **`offset_y`**: Vertical offset of the sprite from the entity's origin. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated by the physics system. Set to `0` (false), meaning it's likely controlled by the verlet chain logic directly.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated by the physics system. Set to `0` (false), similar to `update_transform`.

## Entity Structure

This entity is a simple container for the `SpriteComponent`. It doesn't contain other complex components like physics, AI, or damage handling, suggesting its behavior is primarily dictated by the verlet chain system it belongs to.

### Key Elements:

*   **`<Entity>`**: The root element for this game object.
*   **`<SpriteComponent>`**: As detailed above, this is the sole component defining the visual aspect of the vine segment.

This entity's purpose is to provide a visual anchor point within a verlet chain, allowing for the dynamic and flexible rendering of blue vines.