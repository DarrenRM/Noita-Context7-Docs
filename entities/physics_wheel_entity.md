---
title: Physics Wheel Entity
category: entities
---

# Physics Wheel Entity

This document describes the `physics_wheel.xml` entity, a prop designed for use in Noita's physics engine. It functions as a basic wheel that can be attached to surfaces and potentially driven by a motor.

## Key Components and Attributes

### Base Entity

The entity inherits from `data/entities/base_item_physics.xml`, providing fundamental physics and item properties.

### PhysicsImageShapeComponent

This component defines the visual representation and physical shape of the wheel.

*   **`image_file`**: `data/props_gfx/wheel.png` - Specifies the texture used for the wheel.
*   **`material`**: `wood_prop` - Assigns a material property, influencing its interaction with other physics objects.

### PhysicsBodyComponent

This component governs the physical behavior of the wheel.

*   **`angular_damping`**: `0.01` - Controls how quickly rotational velocity decreases.
*   **`gridworld_box2d`**: `0` - Indicates it's not strictly bound to the grid for its physics simulation.
*   **`linear_damping`**: `0.1` - Controls how quickly linear velocity decreases.
*   **`force_add_update_areas`**: `1` - Ensures the physics updates are applied even if the object is not actively in view.
*   **`randomize_init_velocity`**: `1` - Allows for a slight random initial velocity upon creation.

### PhysicsJointComponent

This component defines how the wheel is attached and potentially driven.

*   **`nail_to_wall`**: `1` - Suggests the wheel can be "nailed" or fixed to a wall.
*   **`pos_x`**: `30`, **`pos_y`**: `30` - Defines the offset of the joint relative to the entity's origin.
*   **`grid_joint`**: `1` - Indicates the joint is aligned with the grid.
*   **`mMotorEnabled`**: `1` - Enables the motor functionality for the joint.
*   **`mMotorSpeed`**: `1` - Sets the target speed for the motor.
*   **`mMaxMotorTorque`**: `500` - Defines the maximum torque the motor can apply.

### CameraBoundComponent

This component manages the entity's visibility and behavior relative to the camera.

*   **`max_count`**: `100` - Limits the total number of these entities that can exist simultaneously.
*   **`distance`**: `1000` - Sets the maximum distance from the camera at which the entity will be rendered or simulated.