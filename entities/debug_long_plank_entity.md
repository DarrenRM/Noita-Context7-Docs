---
title: Debug Long Plank Entity
category: entities
---

# Debug Long Plank Entity

This entity defines a long plank composed of multiple connected segments, primarily for debugging physics interactions.

## Core Components

### PhysicsBody2Component

This component defines the fundamental physics properties of the entity.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `allow_sleep`         | Whether the physics body can enter a sleep state when inactive.          |
| `angular_damping`     | Resistance to rotational movement.                                       |
| `linear_damping`      | Resistance to linear movement.                                           |
| `kill_entity_after_initialized` | If true, the entity is removed from the game after its physics are set up. |

### PhysicsImageShapeComponent

This component defines the visual and physical shape of individual segments of the plank. Multiple instances are used to create the full length.

| Attribute    | Description                                                              |
| :----------- | :----------------------------------------------------------------------- |
| `body_id`    | Unique identifier for the physics body this shape is attached to.        |
| `offset_x`   | Horizontal offset of the shape from the entity's origin.                 |
| `offset_y`   | Vertical offset of the shape from the entity's origin.                   |
| `image_file` | Path to the image file used for the shape's appearance.                  |
| `material`   | The physics material applied to this shape (e.g., `wood_prop`).          |

**Key Observations:**
*   Each `PhysicsImageShapeComponent` uses the same `image_file` (`data/props_breakable_gfx/long_plank_a_00.png`).
*   The `offset_x` attribute is incremented by 64 for each subsequent shape, creating a linear arrangement.
*   All shapes are assigned to the `wood_prop` material.

### PhysicsJoint2Component

These components connect individual `PhysicsImageShapeComponent` segments together using weld joints.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `type`      | The type of joint used (here, `WELD_JOINT` for fixed connections).       |
| `offset_x`  | Horizontal offset of the joint from the entity's origin.                 |
| `offset_y`  | Vertical offset of the joint from the entity's origin.                   |
| `body1_id`  | The `body_id` of the first physics body to connect.                      |
| `body2_id`  | The `body_id` of the second physics body to connect.                     |

**Key Observations:**
*   All joints are of type `WELD_JOINT`, meaning the connected segments are rigidly fixed to each other.
*   Each joint connects two consecutive `body_id`s (e.g., 0 to 1, 1 to 2, etc.).
*   The `offset_x` for the joints is slightly offset from the center of the shapes they connect, likely to ensure a stable weld.

## Entity Structure

The entity is constructed by:
1.  Defining a single `PhysicsBody2Component` for the entire entity.
2.  Creating multiple `PhysicsImageShapeComponent` instances, each representing a segment of the plank and positioned sequentially using `offset_x`.
3.  Connecting these segments using `PhysicsJoint2Component` instances of type `WELD_JOINT`.

This setup effectively creates a single, long, rigid object from multiple smaller physics shapes. The `kill_entity_after_initialized="1"` attribute suggests this is a temporary entity used for testing or debugging physics behavior.