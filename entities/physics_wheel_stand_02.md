---
title: Physics Wheel Stand 02
category: entities
---

# Physics Wheel Stand 02

This entity represents a physics-based wheel stand, likely used as a decorative or functional prop in the game world. It consists of two distinct physics bodies connected by a joint, allowing for rotational movement.

## Key Components

### PhysicsBodyComponent (UID 1)

This component defines the static base of the wheel stand.

*   **`is_static="1"`**: The base is fixed and does not move.
*   **`fixed_rotation="1"`**: The base cannot rotate.
*   **`update_entity_transform="1"`**: The entity's transform is updated based on this body.
*   **`on_death_leave_physics_body="1"`**: The physics body persists even if the entity is destroyed.

### PhysicsImageShapeComponent (for UID 1)

This component associates a visual sprite with the static base.

*   **`image_file="data/props_gfx/wheel_stand_02.png"`**: The sprite for the base.
*   **`material="wood_player_b2"`**: The material properties for collision and interaction.

### PhysicsBodyComponent (UID 2)

This component defines the movable wheel part of the stand.

*   **`fixed_rotation="0"`**: The wheel is allowed to rotate.
*   **`angular_damping="0.1"`**: Provides some resistance to rotation.
*   **`update_entity_transform="0"`**: The entity's transform is not directly updated by this body.
*   **`on_death_leave_physics_body="1"`**: The physics body persists even if the entity is destroyed.

### PhysicsImageShapeComponent (for UID 2)

This component associates a visual sprite with the wheel.

*   **`image_file="data/props_gfx/wheel_stand_wheel_02.png"`**: The sprite for the wheel.
*   **`z="-1"`**: This likely places the wheel sprite behind the base sprite.
*   **`material="wood_prop"`**: The material properties for collision and interaction.

### PhysicsJointComponent

This component connects the two physics bodies and defines their interaction.

*   **`body1_id="1"`**: Refers to the static base body.
*   **`body2_id="2"`**: Refers to the movable wheel body.
*   **`pos_x="14"`, `pos_y="16"`**: The offset from the base body's origin where the joint is attached.
*   **`mMotorEnabled="1"`**: Enables a motor to drive the joint.
*   **`mMotorSpeed="1"`**: Sets the speed of the motor.
*   **`mMaxMotorTorque="105"`**: The maximum torque the motor can apply.
*   **`grid_joint="1"`**: Indicates this is a grid-based joint.

### CameraBoundComponent

*   **`max_count="50"`**: Limits the number of these entities that can be active within the camera's view.
*   **`distance="500"`**: The maximum distance from the camera at which this entity will be considered.