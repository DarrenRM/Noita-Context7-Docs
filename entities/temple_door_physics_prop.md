---
title: Temple Door (Physics Prop)
category: entities
---

# Temple Door (Physics Prop)

This entity defines a physics-based temple door prop in Noita. It utilizes multiple physics components to simulate its behavior and appearance.

## Key Components

### Base Item Physics
This entity inherits from `base_item_physics.xml`, providing fundamental physics properties.

### PhysicsImageShapeComponent
This component defines the visual representation and collision shape of the prop.

*   **`image_file`**: Specifies the sprite for the component.
    *   `data/props_gfx/temple_door_wheel.png`
    *   `data/props_gfx/temple_door_notched.png`
*   **`material`**: The material type, affecting physics interactions.
    *   `metal_prop`
*   **`body_id`**: Unique identifier for the physics body associated with this shape.
    *   `1` (for the wheel)
    *   `2` (for the notched part)

### PhysicsBodyComponent
This component defines the physical properties of the entity's body.

*   **`uid`**: Unique identifier for the physics body.
    *   `1`
    *   `2`
*   **`allow_sleep`**: Whether the body can enter a sleeping state when inactive.
    *   `1` (enabled)
*   **`angular_damping`**: Resistance to rotational motion.
    *   `0.01`
*   **`linear_damping`**: Resistance to linear motion.
    *   `0.1` (for body 1)
    *   `0.03` (for body 2)
*   **`gridworld_box2d`**: Enables Box2D physics within the grid world.
    *   `1`
*   **`force_add_update_areas`**: Forces the addition of update areas for this body.
    *   `1`
*   **`randomize_init_velocity`**: Whether to randomize initial velocity.
    *   `0` (disabled)
*   **`kills_entity`**: Whether this body kills other entities on contact.
    *   `0` (disabled for body 2)

### PhysicsJointComponent
This component defines a joint connecting two physics bodies.

*   **`body1_id`**: The ID of the first body in the joint.
    *   `1`
*   **`body2_id`**: The ID of the second body in the joint.
    *   `1` (This indicates a joint connecting the body to itself, likely for a pivot or hinge effect on a single complex object).
*   **`nail_to_wall`**: Whether the joint is fixed to a wall.
    *   `1` (enabled)
*   **`pos_x`**, **`pos_y`**: The position of the joint in grid coordinates.
    *   `46.5`, `44.5`
*   **`grid_joint`**: Enables grid-based joint behavior.
    *   `1`
*   **`mMotorEnabled`**: Whether a motor is enabled for the joint.
    *   `0` (disabled)
*   **`mMotorSpeed`**: The target speed for the motor.
    *   `-1`
*   **`mMaxMotorTorque`**: The maximum torque the motor can apply.
    *   `500000`

## Disabled Components (Commented Out)

The following components are present but commented out, indicating they are not currently active for this entity.

### LuaComponent
This component would execute a Lua script.

*   **`script_source_file`**: `data/scripts/props/physics_templedoor.lua`

### CameraBoundComponent
This component likely controls how the entity interacts with the camera's view.

*   **`max_count`**: `20`
*   **`distance`**: `1000`