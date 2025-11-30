---
title: Empty Circle Entity
category: entities
---

# Empty Circle Entity

This document describes the `empty_circle.xml` entity, designed for AI-assisted modding of Noita. This entity is a simple, invisible circle that consumes nearby cells.

## Key Components and Attributes

### `CellEaterComponent`

This component defines the primary behavior of the entity: consuming cells within its radius.

*   **`eat_probability`**: `100`
    *   Determines the likelihood of a cell being eaten. A value of `100` means cells within the radius are always eaten.
*   **`radius`**: `48`
    *   The size of the circular area around the entity where cell eating occurs.
*   **`ignored_material`**: `rock_static_cursed`
    *   Specifies materials that the `CellEaterComponent` will *not* consume. In this case, `rock_static_cursed` is ignored.

### `LifetimeComponent`

This component controls how long the entity exists before being removed from the game.

*   **`lifetime`**: `10`
    *   The duration in seconds for which the entity will remain active. After `10` seconds, the entity will be destroyed.

## Other Components

*   **`InheritTransformComponent`**: This component is present but empty, indicating that the entity inherits its transformation (position, rotation, scale) from its parent or the environment. It doesn't define any specific transform properties itself.