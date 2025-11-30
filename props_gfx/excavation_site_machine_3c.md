---
title: Excavation Site Machine 3C
category: data/entities
---

---

# Excavation Site Machine 3C

This entity represents a specific machine found at excavation sites in Noita. It's composed of multiple physics bodies and a joint to simulate its mechanical parts.

## Key Components

### Transform
This component defines the entity's initial position, rotation, and scale in the game world.

*   `position.x`, `position.y`: Initial coordinates.
*   `rotation`: Initial rotation angle.
*   `scale.x`, `scale.y`: Initial scaling factors.

### PhysicsBodyComponent (Body 1)
This is the main static body for the machine's core structure.

*   `uid`: Unique identifier for the physics body.
*   `is_static`: Set to `1` to make this body immovable.
*   `fixed_rotation`: Set to `1` to prevent rotation.
*   `update_entity_transform`: Set to `1` to synchronize entity transform with this body.

### PhysicsImageShapeComponent (Body 1)
Defines the visual representation and collision shape for the main body using an image.

*   `body_id`: Links this shape to `PhysicsBodyComponent` with `uid="1"`.
*   `image_file`: Path to the sprite for the machine's main body (`data/props_gfx/excavationsite_machine_3c.png`).
*   `material`: The physics material applied to this shape (`wood_player_b2`).

### PhysicsBodyComponent (Body 2)
This component defines a movable part of the machine, likely a wheel or rotating mechanism.

*   `uid`: Unique identifier for this physics body.
*   `fixed_rotation`: Set to `0` to allow rotation.
*   `update_entity_transform`: Set to `0` as its transform is managed by the joint.

### PhysicsImageShapeComponent (Body 2)
Defines the visual representation and collision shape for the rotating part.

*   `body_id`: Links this shape to `PhysicsBodyComponent` with `uid="2"`.
*   `image_file`: Path to the sprite for the rotating part (`data/props_gfx/excavationsite_machine_3c_wheel_1.png`).
*   `z`: Specifies the rendering layer (`-1` indicates it's behind the main body).
*   `material`: The physics material applied (`wood_prop`).

### PhysicsJointComponent
This component connects the two physics bodies, simulating a joint with motor functionality.

*   `body1_id`: The `uid` of the first connected body (the static main body).
*   `body2_id`: The `uid` of the second connected body (the rotating part).
*   `pos_x`, `pos_y`: The local offset from `body1` where the joint is attached.
*   `mMotorEnabled`: Set to `1` to enable the motor.
*   `mMotorSpeed`: The target speed of the motor.
*   `mMaxMotorTorque`: The maximum torque the motor can apply.
*   `grid_joint`: Set to `1` to indicate this is a grid-based joint.

### CameraBoundComponent
This component controls how the entity interacts with the camera's view.

*   `max_count`: Maximum number of this entity type that can be active within the camera's bounds.
*   `distance`: The distance from the camera within which this entity is considered active.