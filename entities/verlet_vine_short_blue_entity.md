---
title: Verlet Vine Short Blue Entity
category: entities
---

# Verlet Vine Short Blue Entity

This document describes the `verlet_vine_short_blue.xml` entity, which defines a short, blue vine using Noita's Verlet physics system.

## Entity Structure

The entity is composed of several components that define its physical behavior, appearance, and interactions.

### VerletPhysicsComponent

This component governs the physics simulation of the vine.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `num_points`          | The number of points used to simulate the vine's chain.                     |
| `stiffness`           | Controls how rigid the vine is. Higher values mean less bending.            |
| `velocity_dampening`  | Reduces the velocity of the vine's points over time, simulating friction.   |
| `resting_distance`    | The ideal distance between adjacent points when the vine is at rest.        |
| `pixelate_sprite_transforms` | Enables pixelation effects on the sprite transformations.                 |
| `follow_entity_transform` | If set to 1, the vine will follow the transform of another entity.        |
| `simulate_wind`       | Enables wind simulation for the vine.                                       |
| `wind_change_speed`   | Controls how quickly the wind's direction and intensity change.             |
| `simulate_gravity`    | Enables gravity simulation for the vine.                                    |

### Base Components

These components define the visual segments of the vine. Each `<Base>` tag points to a separate XML file containing the sprite and collision data for a specific part of the vine.

*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_3.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_5.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_8.xml`

### MoveToSurfaceOnCreateComponent

This component ensures that the vine attaches itself to a surface upon creation.

| Attribute                | Description                                                                 |
| :----------------------- | :-------------------------------------------------------------------------- |
| `lookup_radius`          | The radius within which the component searches for a surface to attach to.  |
| `verlet_min_joint_distance` | The minimum distance between joints required for attachment.                |
| `type`                   | Specifies the type of attachment, in this case, `VERLET_ROPE_ONE_JOINT`.    |

### AudioComponent

This component handles the sound effects associated with the vine.

| Attribute   | Description                                                                 |
| :---------- | :-------------------------------------------------------------------------- |
| `file`      | The audio bank file containing the sound events.                            |
| `event_root`| The root event name for collision sounds related to this vine.              |