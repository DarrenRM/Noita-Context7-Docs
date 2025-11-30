---
title: Physics Candle 2
category: entities
---

# Physics Candle 2

This document describes the `physics_candle_2.xml` entity, a physics-enabled candle prop in Noita.

## Key Components

### Base Entity

The entity inherits from `base_item_physics2.xml`, providing fundamental physics and item properties.

### PhysicsBody2Component

*   `kill_entity_after_initialized`: Set to `0`, meaning the entity will not be destroyed immediately after its physics are initialized.

### PhysicsImageShapeComponent

*   `image_file`: Specifies the graphical representation of the candle: `data/props_gfx/physics_candle_2.png`.
*   `material`: Defines the physical material of the candle as `wax_b2`.

### InheritTransformComponent

This component is used to offset the position of a child entity relative to the main entity.

*   `Transform`:
    *   `position.x`: `-0.5`
    *   `position.y`: `-2`

### ElectricityComponent

This component grants the candle electrical properties.

*   `energy`: Set to `5`, indicating the amount of energy associated with this component.
*   `hack_is_set_fire`: Set to `1`, meaning this component can trigger the entity to catch fire.