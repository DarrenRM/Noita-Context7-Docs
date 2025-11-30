---
title: Short Verlet Cord Entity
category: entities
---

# Short Verlet Cord Entity

This entity defines a short, flexible cord using Noita's Verlet physics system. It's designed to be attached to surfaces and exhibit realistic swinging and stretching behavior.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the cord.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `num_points`          | The number of segments the cord is divided into. (8 in this case)           |
| `stiffness`           | How rigid the cord is. Higher values mean less stretching. (1.0)            |
| `velocity_dampening`  | How quickly the cord's movement slows down. (0.9)                           |
| `resting_distance`    | The ideal distance between points when not under tension. (4)               |
| `pixelate_sprite_transforms` | Whether to apply pixelation effects to the cord's sprite. (1 = enabled) |
| `follow_entity_transform` | Whether the cord should follow the transform of another entity. (0 = disabled) |
| `simulate_wind`       | Whether wind forces affect the cord. (1 = enabled)                          |
| `wind_change_speed`   | How quickly wind direction and strength change. (0.25)                      |
| `simulate_gravity`    | Whether gravity affects the cord. (1 = enabled)                             |

### Base Components

These components define the visual segments of the cord. Each `<Base>` tag points to a separate XML file defining a part of the cord's visual appearance and potentially its physics properties.

*   `data/entities/verlet_chains/cords/cord_parts/cord_verlet_a_1.xml`
*   `data/entities/verlet_chains/cords/cord_parts/cord_verlet_a_2.xml`
*   `data/entities/verlet_chains/cords/cord_parts/cord_verlet_a_3.xml`
*   `data/entities/verlet_chains/cords/cord_parts/cord_verlet_a_5.xml`
*   `data/entities/verlet_chains/cords/cord_parts/cord_verlet_a_6.xml`
*   `data/entities/verlet_chains/cords/cord_parts/cord_verlet_a_7.xml`
*   `data/entities/verlet_chains/cords/cord_parts/cord_verlet_a_8.xml`

### MoveToSurfaceOnCreateComponent

This component ensures that when the cord is created, it attaches itself to the nearest suitable surface.

| Attribute                | Description                                                              |
| :----------------------- | :----------------------------------------------------------------------- |
| `lookup_radius`          | The radius to search for a surface to attach to. (28)                    |
| `verlet_min_joint_distance` | The minimum distance between joints when attaching to a surface. (14)    |
| `type`                   | Specifies the type of attachment. `VERLET_ROPE_ONE_JOINT` indicates a single attachment point. |