---
title: Physics Wheel Stand 03
category: data
---

# Physics Wheel Stand 03

This entity represents a physics-based wheel stand prop, likely used for decorative or functional purposes within the game environment. It consists of two distinct physics bodies and a joint connecting them, allowing for rotational movement.

## Key Components

### PhysicsBodyComponent (Body 1)

This component defines the static base of the wheel stand.

*   **`uid`**: `1` (Unique identifier for this physics body)
*   **`fixed_rotation`**: `1` (The body's rotation is locked)
*   **`is_static`**: `1` (The body is immovable)
*   **`update_entity_transform`**: `1` (Its transform is updated by the physics engine)
*   **`on_death_leave_physics_body`**: `1` (Leaves a physics body upon destruction)

### PhysicsImageShapeComponent (Shape for Body 1)

This component defines the visual representation and collision shape for the static base.

*   **`body_id`**: `1` (Links to `PhysicsBodyComponent` with `uid="1"`)
*   **`image_file`**: `data/props_gfx/wheel_stand_03.png` (The sprite for the base)
*   **`material`**: `wood_player_b2` (The physics material applied)

### PhysicsBodyComponent (Body 2)

This component defines the movable wheel part of the stand.

*   **`uid`**: `2` (Unique identifier for this physics body)
*   **`fixed_rotation`**: `0` (The body's rotation is not locked)
*   **`angular_damping`**: `0.1` (Reduces rotational velocity over time)
*   **`linear_damping`**: `0` (No linear velocity reduction)
*   **`update_entity_transform`**: `0` (Its transform is not directly updated by the physics engine, likely controlled by the joint)
*   **`on_death_leave_physics_body`**: `1` (Leaves a physics body upon destruction)

### PhysicsImageShapeComponent (Shape for Body 2)

This component defines the visual representation and collision shape for the wheel.

*   **`body_id`**: `2` (Links to `PhysicsBodyComponent` with `uid="2"`)
*   **`image_file`**: `data/props_gfx/wheel_stand_wheel_03.png` (The sprite for the wheel)
*   **`z`**: `-1` (Renders behind the base)
*   **`material`**: `wood_prop` (The physics material applied)

### PhysicsJointComponent

This component connects the two physics bodies, creating a revolute joint (like a hinge or axle).

*   **`body1_id`**: `1` (Connects to the static base)
*   **`body2_id`**: `2` (Connects to the wheel)
*   **`pos_x`**: `45` (X-coordinate of the joint relative to body1)
*   **`pos_y`**: `31` (Y-coordinate of the joint relative to body1)
*   **`mMotorEnabled`**: `1` (The motor for this joint is active)
*   **`mMotorSpeed`**: `1` (The target speed of the motor)
*   **`mMaxMotorTorque`**: `100` (The maximum torque the motor can apply)
*   **`grid_joint`**: `1` (Indicates this is a grid-aligned joint)

### CameraBoundComponent

This component controls how the entity interacts with the camera.

*   **`max_count`**: `50` (Maximum number of this entity type that can be active within camera bounds)
*   **`distance`**: `500` (The distance from the camera within which this entity is considered active)