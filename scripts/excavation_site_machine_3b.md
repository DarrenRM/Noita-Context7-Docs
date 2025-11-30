---
title: Excavation Site Machine 3B
category: data/entities
---

# Excavation Site Machine 3B

This entity represents a complex, multi-part machine found at excavation sites in Noita. It features a central static body with three rotating wheels, connected via physics joints.

## Core Components

### `_Transform`
Defines the entity's initial position, rotation, and scale.

### `PhysicsBodyComponent`
This entity utilizes multiple `PhysicsBodyComponent` instances to define its physical properties.

*   **`uid`**: Unique identifier for each physics body.
*   **`is_static`**: Determines if the body is fixed in place. The main body (`uid="1"`) is static.
*   **`fixed_rotation`**: If `1`, the body's rotation is locked. The main body is fixed.
*   **`linear_damping` / `angular_damping`**: Controls how quickly the body loses linear and angular velocity.
*   **`auto_clean`**: If `1`, the body is removed when it goes off-screen. Set to `0` for this entity.
*   **`on_death_leave_physics_body`**: If `1`, the physics body persists after the entity is destroyed.

### `PhysicsImageShapeComponent`
Defines the visual representation and collision shape for each physics body.

*   **`body_id`**: Links the shape to a specific `PhysicsBodyComponent`.
*   **`image_file`**: Path to the sprite for the component.
*   **`material`**: The material type, affecting physics interactions (e.g., `wood_player_b2`, `wood_prop`).
*   **`centered`**: If `1`, the image is centered on the body's origin.
*   **`z`**: Z-order for rendering, used here to place wheels behind the main body.

### `PhysicsJointComponent`
Connects different physics bodies together, simulating mechanical linkages.

*   **`body1_id` / `body2_id`**: The UIDs of the two bodies being connected.
*   **`pos_x` / `pos_y`**: The local position of the joint on `body1`.
*   **`mMotorEnabled`**: If `1`, a motor is active for this joint.
*   **`mMotorSpeed`**: The target speed for the motor.
*   **`mMaxMotorTorque`**: The maximum torque the motor can apply.
*   **`grid_joint`**: If `1`, the joint is aligned with the grid.

### `CameraBoundComponent`
Controls how the entity interacts with the camera.

*   **`distance`**: The maximum distance from the camera before the entity might be culled or affected.
*   **`max_count`**: Maximum number of this entity type that can be active within the camera bounds.

## Key Attributes & Elements

| Component Type          | Key Attributes/Elements