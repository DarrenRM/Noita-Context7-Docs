---
title: Physics Logo Entity
category: entities
---

---

# Physics Logo Entity

This document describes the `physics_logo.xml` entity, which represents a physics-enabled logo prop in Noita.

## Core Components

The `physics_logo.xml` entity utilizes several key components to define its behavior and appearance:

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the logo.

| Attribute      | Description                                     |
|----------------|-------------------------------------------------|
| `centered`     | If `1`, the image is centered on the entity.    |
| `image_file`   | Path to the image file used for the logo.       |
| `material`     | The material type that influences physics.      |

### PhysicsBodyComponent

This component governs the physics simulation of the entity.

| Attribute               | Description                                                              |
|-------------------------|--------------------------------------------------------------------------|
| `allow_sleep`           | If `1`, the body can enter a sleep state when inactive to save performance. |
| `angular_damping`       | Reduces rotational velocity over time.                                   |
| `gridworld_box2d`       | If `0`, uses standard Box2D physics.                                     |
| `linear_damping`        | Reduces linear velocity over time.                                       |
| `force_add_update_areas`| If `1`, forces the entity to be added to update areas.                   |
| `randomize_init_velocity`| If `1`, applies a random initial velocity.                               |
| `fixed_rotation`        | If `0`, the body can rotate freely.                                      |
| `is_bullet`             | If `0`, the body is not treated as a bullet.                             |

### PhysicsJointComponent

This component allows the logo to be attached to the environment.

| Attribute   | Description                                     |
|-------------|-------------------------------------------------|
| `nail_to_wall`| If `1`, the joint acts like a nail, fixing it to a wall. |
| `pos_x`     | X-coordinate offset for the joint.              |
| `pos_y`     | Y-coordinate offset for the joint.              |
| `grid_joint`| If `1`, uses grid-based joint positioning.      |

### CameraBoundComponent

This component controls the entity's visibility and behavior relative to the camera.

| Attribute   | Description                                     |
|-------------|-------------------------------------------------|
| `max_count` | Maximum number of this entity type that can be active. |
| `distance`  | The distance from the camera at which the entity is considered. |

## Child Entities

The `physics_logo.xml` entity can also contain other entities, often used to create variations or more complex logo designs. These are typically defined using `<Base file="...">` to inherit properties from other entity files.

Example:
```xml
<Entity name="1">
    <Base file="data/entities/props/physics_logo_1.xml"></Base>
</Entity>
```
This indicates that entity "1" is based on the `physics_logo_1.xml` file.