---
title: Physics Fungus Behavior
category: scripts
---

---

# Physics Fungus Behavior

This script defines the dynamic behavior of "physics fungus" entities in Noita, primarily focusing on rotational twisting and vertical lifting.

## Core Mechanics

### Twisting Effect

The fungus exhibits a twisting motion, driven by a procedural animation based on game frame number and entity ID.

*   **`is_in_camera_bounds(x,y,50)`**: Activates the twisting effect only when the fungus is within a certain proximity to the camera, optimizing performance.
*   **`ProceduralRandomf(entity_id, 4, 0.1, 0.75)`**: Determines a random speed multiplier for the twist, ensuring variation between different fungus instances.
*   **`edit_all_components2("PhysicsJoint2MutatorComponent", ...)`**: Modifies the `motor_speed` of `PhysicsJoint2MutatorComponent` instances.
    *   The speed is calculated using `math.sin` with a time-dependent offset (`t`) and a joint-specific offset (`time_offset`).
    *   The direction of the twist alternates between joints (`joint == 1` vs. others).

### Lifting Effect

The fungus can also exert an upward force, simulating a lifting action.

*   **`get_variable_storage_component(entity_id, "lift")`**: Utilizes a variable storage component to manage the lifting force. This allows for more consistent behavior across different fungus sizes.
*   **`PhysicsApplyForce(entity_id, 0, comp.value_int)`**: Applies a vertical force (along the Y-axis) based on the `value_int` stored in the lift component.

## Key Components Targeted

*   **`PhysicsJoint2MutatorComponent`**: Crucial for implementing the twisting motion by controlling joint motors.
*   **Variable Storage Component**: Used to store and retrieve the lifting force value.