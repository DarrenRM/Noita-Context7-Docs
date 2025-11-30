---
title: Verlet Vine Long Entity
category: entities
---

# Verlet Vine Long Entity

This document describes the `verlet_vine_long.xml` entity, which defines a long, flexible vine structure in Noita. It utilizes the Verlet physics system to simulate its movement and behavior.

## Entity Structure

The `verlet_vine_long.xml` entity is composed of several key components that define its physical properties, appearance, and interactions.

### VerletPhysicsComponent

This component governs the physics simulation of the vine.

| Attribute              | Description                                                                                                |
| :--------------------- | :--------------------------------------------------------------------------------------------------------- |
| `num_points`           | The number of points used to define the vine's chain. Higher values result in a more detailed and flexible vine. |
| `stiffness`            | Controls how rigid the vine is. A value of `1.0` indicates a relatively stiff vine.                         |
| `velocity_dampening`   | Reduces the velocity of the vine's points over time, simulating air resistance or internal friction.       |
| `resting_distance`     | The ideal distance between adjacent points in the vine when it's not under stress.                         |
| `pixelate_sprite_transforms` | Enables pixelation effects on the sprite transformations, contributing to the visual style.                |
| `follow_entity_transform` | If set to `1`, the vine would follow the transform of another entity. Set to `0` here.                   |
| `simulate_wind`        | Enables wind simulation for the vine.                                                                      |
| `wind_change_speed`    | Controls how quickly the wind's direction and intensity change.                                            |
| `simulate_gravity`     | Enables gravity simulation for the vine.                                                                   |

### Base Components

The vine is constructed from multiple smaller vine segments defined in separate XML files. These `Base` tags effectively assemble the long vine from these pre-defined parts.

*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_b_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_b_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_b_3.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_b_4.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_b_5.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_b_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_b_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_b_8.xml`

*(Note: Some vine parts are repeated to create the desired length and visual pattern.)*

### MoveToSurfaceOnCreateComponent

This component ensures that the vine attaches itself to a surface upon creation.

| Attribute                | Description                                                                                             |
| :----------------------- | :------------------------------------------------------------------------------------------------------ |
| `lookup_radius`          | The radius around the vine's spawn point to search for a surface to attach to.                          |
| `verlet_min_joint_distance` | The minimum distance between joints that must be maintained when attaching to a surface.                |
| `type`                   | Specifies the type of Verlet rope attachment. `VERLET_ROPE_TWO_JOINTS` indicates a two-point attachment. |

### AudioComponent

This component handles the sound effects associated with the vine.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `file`      | The audio bank file containing the sound events.                         |
| `event_root` | The root event name for vine-related audio, specifically for collisions. |