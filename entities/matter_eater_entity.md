---
title: Matter Eater Entity
category: entities
---

# Matter Eater Entity

This document describes the `matter_eater.xml` entity, a component that consumes nearby materials in Noita.

## Core Functionality

The `CellEaterComponent` is the primary driver of this entity's behavior. It's responsible for identifying and consuming adjacent "cells" (materials) within its defined radius.

### Key Attributes of `CellEaterComponent`

*   **`eat_probability`**: (Number) The chance (0-100) that the entity will attempt to eat a material when it's within range. A value of `90` means it has a 90% chance.
*   **`radius`**: (Number) The distance from the entity within which it will attempt to consume materials. `8` is the specified radius.
*   **`ignored_material`**: (String) A specific material that this entity will *not* consume. `rock_static_cursed` is listed as an ignored material.
*   **`ignored_material_tag`**: (String) A tag used to identify materials that should be ignored. `[matter_eater_ignore_list]` is the placeholder for this.

## Lifetime

The `LifetimeComponent` controls how long the Matter Eater entity persists in the game world.

### Key Attributes of `LifetimeComponent`

*   **`lifetime`**: (Number) The base duration in frames the entity will exist. `200` frames.
*   **`randomize_lifetime.min`**: (Number) The minimum reduction from the base `lifetime`. `-50` frames.
*   **`randomize_lifetime.max`**: (Number) The maximum increase to the base `lifetime`. `50` frames.

This means the Matter Eater's total lifetime will be between 150 and 250 frames.

## Inheritance

*   **`InheritTransformComponent`**: This component indicates that the entity inherits transform properties (like position, rotation, scale) from its parent or the environment it's spawned in. It has no specific configurable attributes in this definition.