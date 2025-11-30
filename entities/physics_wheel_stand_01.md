---
title: Physics Wheel Stand 01
category: entities
---

# Physics Wheel Stand 01

This entity represents a static wheel stand with a rotating wheel attached via a physics joint. It's designed to be a prop within the game world.

## Key Components

### PhysicsBodyComponent (UID 1)

This component defines the static properties of the main stand.

*   **`is_static="1"`**: The stand itself does not move.
*   **`fixed_rotation="1"`**: The stand's rotation is locked.
*   **`update_entity_transform="1"`**: The entity's transform is updated based on physics.
*   **`on_death_leave_physics_body="1"`**: When destroyed, it leaves behind a physics body.

### PhysicsImageShapeComponent (Body ID 1)

This component defines the visual shape and material for the static stand.

*   **`image_file="data/props_gfx/wheel_stand_01.png"`**: Specifies the sprite for the stand.
*   **`material="wood_player_b2"`**: The physics material applied to the stand.

### PhysicsBodyComponent (UID 2)

This component defines the properties of the rotating wheel.

*   **`fixed_rotation="0"`**: The wheel is allowed to rotate freely.
*   **`angular_damping="0.1"`**: Provides some resistance to rotation.
*   **`update_entity_transform="0"`**: The entity's transform is not directly updated by this body's physics.
*   **`on_death_leave_physics_body="1"`**: When destroyed, it leaves behind a physics body.

### PhysicsImageShapeComponent (Body ID 2)

This component defines the visual shape and material for the rotating wheel.

*   **`image_file="data/props_gfx/wheel_stand_wheel_01.png"`**: Specifies the sprite for the wheel.
*   **`z="-1"`**: Renders the wheel behind the stand.
*   **`material="wood_prop"`**: The physics material applied to the wheel.

### PhysicsJointComponent

This component connects the static stand (body1\_id="1") to the rotating wheel (body2\_id="2") and defines its rotational behavior.

*   **`body1_id="1"`**: The ID of the static body (the stand).
*   **`body2_id="2"`**: The ID of the dynamic body (the wheel).
*   **`pos_x="46"`, `pos_y="37"`**: The anchor point of the joint relative to `body1`.
*   **`mMotorEnabled="1"`**: The motor for rotation is active.
*   **`mMotorSpeed="1.5"`**: The target speed of the wheel's rotation.
*   **`mMaxMotorTorque="200"`**: The maximum torque the motor can apply.
*   **`grid_joint="1"`**: Indicates this is a grid-based joint.

### CameraBoundComponent

This component controls how the entity interacts with the camera.

*   **`max_count="50"`**: Limits the number of these entities that can be active within the camera's view.
*   **`distance="500"`**: The maximum distance from the camera at which this entity will be considered.