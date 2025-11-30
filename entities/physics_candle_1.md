---
title: Physics Candle 1
category: entities
---

# Physics Candle 1

This entity defines a physics-enabled candle prop in Noita. It's designed to be interactable and can be set on fire.

## Key Components

### Base Entity (`base_item_physics2.xml`)

This component provides the fundamental physics properties for the candle.

*   **`PhysicsBody2Component`**:
    *   `kill_entity_after_initialized`: Set to `0`, meaning the entity will persist after its physics are initialized.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: Specifies the visual sprite for the candle (`data/props_gfx/physics_candle_1.png`).
    *   `material`: Defines the physical material of the candle, set to `wax_b2`.

### Electrical Interaction (`ElectricityComponent`)

This component allows the candle to interact with electrical effects and can be set on fire.

*   **`energy`**: Set to `5`, indicating the amount of energy it can handle or emit in certain electrical interactions.
*   **`hack_is_set_fire`**: Set to `1`, enabling the candle to be set on fire through electrical means.

### Transform (`InheritTransformComponent`)

This component is used to adjust the position of a child entity relative to the parent.

*   **`Transform`**:
    *   `position.x`: `-0.5` - Offsets the child entity 0.5 units to the left.
    *   `position.y`: `0` - No vertical offset.