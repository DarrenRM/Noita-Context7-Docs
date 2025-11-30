---
title: Physics Grass Prop
category: entities
---

# Physics Grass Prop

This document describes the `physics_grass_01.xml` entity, which represents a destructible grass prop in Noita. It utilizes a chain of physics bodies and joints to simulate the bending and breaking behavior of grass stalks.

## Key Components

### `PhysicsBody2Component`

This component defines the primary physics properties of the grass entity.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `is_static`         | `0` - The body is dynamic and can be affected by physics.                |
| `allow_sleep`       | `1` - The body can enter a sleep state when not in motion to save resources. |
| `angular_damping`   | `0.01` - Resistance to rotational movement.                              |
| `linear_damping`    | `0.3` - Resistance to linear movement.                                   |
| `init_offset_y`     | `8` - Initial vertical offset when the entity is spawned.                |
| `kill_entity_after_initialized` | `1` - The entity is removed after its physics are initialized. |

### `PhysicsImageShapeComponent`

This component defines the visual representation and physical shape of each grass stalk segment. Multiple instances create a segmented appearance.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `body_id`   | Unique identifier for the physics body associated with this shape.       |
| `is_root`   | `1` - Indicates this is the root segment of the grass.                   |
| `offset_x`  | Horizontal offset of the shape relative to its body.                     |
| `offset_y`  | Vertical offset of the shape relative to its body.                       |
| `image_file`| Path to the sprite used for the grass stalk segment (`grass_stalk.png`). |
| `material`  | `fungus_loose` - The material properties affecting physics interactions. |

### `PhysicsJoint2MutatorComponent`

These components are used to control the behavior of joints, specifically their motors.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `joint_id`       | Identifier linking this mutator to a specific `PhysicsJoint2Component`.  |
| `motor_speed`    | `0.001` - The target speed for the joint's motor.                        |
| `motor_max_torque` | `91` - The maximum torque the motor can exert.                           |

### `PhysicsJoint2Component`

These components define the connections between different physics bodies, simulating the structure of the grass.

| Attribute        | Description                                                                                             |
| :--------------- | :------------------------------------------------------------------------------------------------------ |
| `type`           | `REVOLUTE_JOINT` - Creates a hinge-like joint allowing rotation. `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE` attaches to the environment. |
| `joint_id`       | Unique identifier for the joint.                                                                        |
| `offset_x`       | Horizontal offset of the joint relative to `body1`.                                                     |
| `offset_y`       | Vertical offset of the joint relative to `body1`.                                                       |
| `body1_id`       | The ID of the first physics body connected by the joint.                                                |
| `body2_id`       | The ID of the second physics body connected by the joint (for `REVOLUTE_JOINT`).                        |
| `break_force`    | The force required to break the joint.                                                                  |
| `break_distance` | The distance at which the joint will break.                                                             |
| `ray_x`, `ray_y` | Used with `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE` to define the raycast for surface attachment.       |
| `surface_attachment_offset_y` | Vertical offset from the detected surface for attachment.                               |

## Structure Breakdown

The `physics_grass_01.xml` entity is constructed as follows:

1.  **Root Physics Body (`body_id="100"`):** This is the base of the grass, attached to the ground.
2.  **Segmented Stalks (`body_id="101"`, `body_id="102"`):** Each subsequent `PhysicsImageShapeComponent` represents a segment of the grass stalk, stacked vertically.
3.  **Internal Joints (`REVOLUTE_JOINT`):**
    *   `joint_id="1"` connects `body_id="100"` to `body_id="101"`.
    *   `joint_id="2"` connects `body_id="101"` to `body_id="102"`.
    These joints allow the segments to bend relative to each other.
4.  **Ground Attachment (`REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE`):** The topmost stalk segment (`body_id="102"`) is attached to the nearest surface using a special joint type. This ensures the grass stays rooted but can still sway.

The `PhysicsJoint2MutatorComponent` instances likely influence the subtle swaying or movement of the grass stalks by applying a small motor force.