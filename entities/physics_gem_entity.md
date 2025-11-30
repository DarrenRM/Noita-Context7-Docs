---
title: Physics Gem Entity
category: entities
---

# Physics Gem Entity

This document describes the `physics_gem.xml` entity, which represents a basic physics-enabled gem prop in Noita.

## Key Components

### PhysicsBodyComponent
This component defines the physical properties of the gem.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `allow_sleep`       | Whether the physics body can go to sleep when not in motion.             |
| `angular_damping`   | Resistance to rotational motion.                                         |
| `fixed_rotation`    | If true, the object's rotation is locked.                                |
| `is_bullet`         | If true, the object is treated as a bullet (e.g., for collision).        |
| `linear_damping`    | Resistance to linear motion.                                             |
| `auto_clean`        | If true, the physics body is automatically removed when no longer needed. |
| `on_death_leave_physics_body` | If true, the physics body persists even after the entity dies. |

### PhysicsImageShapeComponent
This component defines the visual shape and material of the physics body.

| Attribute    | Description                                                              |
| :----------- | :----------------------------------------------------------------------- |
| `body_id`    | The ID of the `PhysicsBodyComponent` this shape is attached to.          |
| `centered`   | If true, the image is centered on the physics body.                      |
| `image_file` | The path to the image file used for the gem's appearance.                |
| `material`   | The physics material applied to this shape (e.g., `gem_box2d`).          |

### CameraBoundComponent
This component controls how the entity interacts with the camera's view.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `max_count` | The maximum number of these entities that can be active within the camera's view. |
| `distance`  | The maximum distance from the camera at which this entity can exist.     |