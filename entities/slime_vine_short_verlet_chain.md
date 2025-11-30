---
title: Slime Vine Short Verlet Chain
category: entities
---

# Slime Vine Short Verlet Chain

This entity defines a short, flexible slime vine using Noita's Verlet physics system. It's designed to attach to surfaces and exhibit organic, swaying movement.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the vine.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `num_points`          | The number of segments the vine is divided into for physics simulation.     |
| `stiffness`           | Controls how rigid the vine segments are. Higher values mean less bending.  |
| `velocity_dampening`  | Reduces the velocity of the vine segments over time, causing it to settle.  |
| `resting_distance`    | The preferred distance between connected points when no forces are applied. |
| `pixelate_sprite_transforms` | Enables pixelation effects on sprite transformations.                      |
| `follow_entity_transform` | If set to 1, the vine will follow the transform of another entity.        |
| `simulate_wind`       | Enables simulation of wind forces affecting the vine.                       |
| `wind_change_speed`   | Controls how quickly wind direction and strength change.                    |
| `simulate_gravity`    | Enables simulation of gravity affecting the vine.                           |

### Base Components

These `Base` tags link to the actual visual and physical parts of the slime vine.

*   `data/entities/verlet_chains/slime_vine/parts/slime_vine_verlet_1.xml` (appears twice)
*   `data/entities/verlet_chains/slime_vine/parts/slime_vine_verlet_2.xml`

### MoveToSurfaceOnCreateComponent

This component ensures the vine attaches itself to a surface upon creation.

| Attribute                | Description                                                                    |
| :----------------------- | :----------------------------------------------------------------------------- |
| `lookup_radius`          | The radius within which the component searches for a surface to attach to.     |
| `verlet_min_joint_distance` | The minimum distance between joints on the vine when attaching to a surface. |
| `type`                   | Specifies the type of attachment behavior, `VERLET_ROPE_ONE_JOINT` in this case. |