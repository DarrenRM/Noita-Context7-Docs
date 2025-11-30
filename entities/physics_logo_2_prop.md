---
title: Physics Logo 2 Prop
category: entities
---

# Physics Logo 2 Prop

This entity defines a physics-enabled prop that appears as a logo. It's designed to interact with the game's physics engine, allowing it to fall, collide, and be affected by forces.

## Key Components

### `InheritTransformComponent`

This component is present but empty, indicating that the entity inherits its transform properties from its parent or the default entity setup.

### `PhysicsImageShapeComponent`

This is the core visual component.

| Attribute   | Value                               | Description                                                                 |
| :---------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `centered`  | `1`                                 | Centers the image on the entity's origin.                                   |
| `image_file`| `data/props_gfx/logo_2.png`         | Specifies the graphical asset used for the prop.                            |
| `material`  | `wood_loose`                        | Defines the physical material properties, affecting its interaction with physics. |

### `PhysicsBodyComponent`

This component governs the physical behavior of the entity.

| Attribute               | Value | Description                                                                                             |
| :---------------------- | :---- | :------------------------------------------------------------------------------------------------------ |
| `allow_sleep`           | `1`   | Allows the body to enter a sleep state when inactive to save performance.                               |
| `angular_damping`       | `0.01`| Reduces rotational velocity over time.                                                                  |
| `gridworld_box2d`       | `0`   | Disables the use of grid-based physics for this body.                                                   |
| `linear_damping`        | `0.1` | Reduces linear velocity over time.                                                                      |
| `force_add_update_areas`| `1`   | Forces the entity to be added to update areas, ensuring it's processed by the physics engine.           |
| `randomize_init_velocity`| `1`  | Applies a small random initial velocity upon creation.                                                  |
| `fixed_rotation`        | `0`   | Allows the body to rotate freely.                                                                       |
| `is_bullet`             | `0`   | Indicates this is not a projectile.                                                                     |

### `PhysicsJointComponent`

This component attaches the logo to a wall, simulating a fixed but potentially rotatable connection.

| Attribute      | Value | Description                                                                                             |
| :------------- | :---- | :------------------------------------------------------------------------------------------------------ |
| `nail_to_wall` | `1`   | This is a special flag that effectively nails the joint to the nearest wall.                            |
| `pos_x`        | `85`  | X-coordinate offset for the joint's position relative to the entity's origin.                           |
| `pos_y`        | `64.5`| Y-coordinate offset for the joint's position relative to the entity's origin.                           |
| `grid_joint`   | `1`   | Enables grid-based joint behavior.                                                                      |
| `mMotorEnabled`| `1`   | Enables a motor for this joint, allowing for controlled rotation.                                       |
| `mMotorSpeed`  | `-30` | Sets the target speed for the motor. A negative value indicates rotation in one direction.              |
| `mMaxMotorTorque`| `20` | Sets the maximum torque the motor can apply to achieve the target speed.                                |

### `CameraBoundComponent`

This component manages the entity's visibility and behavior relative to the camera.

| Attribute   | Value | Description                                                                                             |
| :---------- | :---- | :------------------------------------------------------------------------------------------------------ |
| `max_count` | `100` | The maximum number of this entity type that can exist within the camera's view.                         |
| `distance`  | `1000`| The maximum distance from the camera at which this entity can be rendered or processed.                 |