---
title: Physics Candle 3
category: entities
---

# Physics Candle 3

This document describes the `physics_candle_3.xml` entity, a physics-enabled candle prop in Noita.

## Key Components

### Base Entity

The entity inherits from `base_item_physics2.xml`, providing fundamental physics and item properties.

*   **`PhysicsBody2Component`**:
    *   `kill_entity_after_initialized`: Set to `0`, meaning the entity will not be destroyed immediately after its physics are initialized.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: Specifies the graphical representation of the candle: `data/props_gfx/physics_candle_3.png`.
    *   `material`: Defines the physical material of the candle as `wax_b2`.

### Attached Entity

An additional entity is attached to the base candle, granting it specific behaviors.

*   **`InheritTransformComponent`**:
    *   `Transform`:
        *   `position.x`: `-0.5` (relative offset)
        *   `position.y`: `2` (relative offset)
        This positions the attached component slightly offset from the candle's origin.
*   **`ElectricityComponent`**:
    *   `energy`: Set to `5`, indicating the amount of energy associated with this component.
    *   `hack_is_set_fire`: Set to `1`, which means this component can trigger fire effects.