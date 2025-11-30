---
title: Boss Limb Entity
category: entities
---

# Boss Limb Entity

This document describes the base entity for boss limbs in Noita, intended for AI-assisted modding. It defines the fundamental components and properties that govern the behavior and appearance of these entities.

## Key Components

### `IKLimbWalkerComponent`

This component is essential for enabling limb-based walking mechanics. While its specific parameters are not detailed in this snippet, its presence indicates that the entity is designed to move as a limb.

### `IKLimbComponent`

This component defines the physical characteristics of the limb.

*   **`length`**: Specifies the length of the limb. In this case, it's set to `80`.

### `SpriteComponent`

This component handles the visual representation of the limb. Multiple `SpriteComponent` instances are used to layer different parts of the limb's sprite.

*   **`image_file`**: The path to the sprite image.
    *   `data/entities/animals/boss_limbs/limb1_A.png`
    *   `data/entities/animals/boss_limbs/limb1_B.png`
    *   `data/entities/animals/boss_limbs/knee.png`
*   **`offset_x`**: Horizontal offset for the sprite.
*   **`offset_y`**: Vertical offset for the sprite.
*   **`update_transform`**: Controls whether the sprite's transform updates with the entity. Set to `0` (false) here.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation updates with the entity. Set to `0` (false) here.
*   **`z_index`**: Determines the drawing order of the sprite. A `z_index` of `10` places it relatively high in the drawing order.

## Inheritance

The `<InheritTransformComponent>` suggests that this entity inherits transformation properties from a parent or base entity, which is common for modular entity design in Noita.

## Usage Notes for Modding

*   To create custom boss limbs, you would typically inherit from this base entity and modify or add components.
*   The `image_file` paths in `SpriteComponent` are crucial for defining the visual appearance. Ensure custom sprites are placed correctly within the game's asset structure.
*   The `IKLimbWalkerComponent` and `IKLimbComponent` are key to defining how the limb moves and interacts with the environment. Further investigation into their specific parameters within the Noita engine or other modding resources would be beneficial.