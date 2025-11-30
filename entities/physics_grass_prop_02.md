---
title: Physics Grass Prop 02
category: entities
---

# Physics Grass Prop 02

This entity defines a physics-based grass prop, designed to sway and break realistically. It's composed of multiple connected physics shapes that simulate a stalk of grass.

## Key Components

### `PhysicsBody2Component`

This component defines the overall physics properties of the grass entity.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `is_static`         | `0` - The grass is not static and can be affected by physics.            |
| `allow_sleep`       | `1` - The physics body can go to sleep when not in motion to save resources. |
| `angular_damping`   | `0.01` - Small value, allowing for some rotation.                        |
| `linear_damping`    | `0.3` - Moderate value, slowing down linear movement.                    |
| `init_offset_y`     | `8` - Initial vertical offset when the entity is spawned.                |
| `kill_entity_after_initialized` | `1` - The entity is removed after its physics are initialized. |

### `PhysicsImageShapeComponent`

These components define the visual and physical shape of the grass stalk segments. Multiple instances create the segmented appearance.

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `body_id`     | Unique identifier for each physics body segment.                         |
| `is_root`     | `1` - Marks the first segment as the root of the physics chain.          |
| `offset_y`    | Vertical offset of the shape relative to its parent body.                |
| `image_file`  | Path to the sprite used for this segment (`data/props_gfx/grass_stalk.png`). |
| `material`    | `fungus_loose` - The material properties affecting physics interactions. |

### `PhysicsJoint2Component`

These components connect the individual `PhysicsImageShapeComponent` segments, creating a chain-like structure.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `type`          | `REVOLUTE_JOINT` - Creates a hinge-like connection allowing rotation.    |
| `joint_id`      | Unique identifier for each joint.                                        |
| `offset_x`, `offset_y` | Offset of the joint relative to the connected bodies.                |
| `body1_id`, `body2_id` | The IDs of the physics bodies being connected.                       |
| `break_force`   | The force required to break the joint.                                   |
| `break_distance`| The distance at which the joint will break.                              |

### `PhysicsJoint2Component` (Surface Attachment)

This special joint connects the bottom-most grass segment to the nearby ground surface.

| Attribute                      | Description                                                              |
| :----------------------------- | :----------------------------------------------------------------------- |
| `type`                         | `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE` - Attaches to the ground.      |
| `offset_x`, `offset_y`         | Offset of the attachment point.                                          |
| `body1_id`                     | The ID of the physics body to attach (the lowest grass segment).         |
| `break_force`                  | The force required to break the connection to the surface.               |
| `break_distance`               | The distance at which the connection to the surface will break.          |
| `ray_x`, `ray_y`               | Defines the direction and length of the raycast for surface detection. |
| `surface_attachment_offset_y`  | Vertical offset from the detected surface for attachment.                |