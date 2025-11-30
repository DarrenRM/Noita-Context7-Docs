---
title: Verlet Vine Long Blue
category: entities
---

# Verlet Vine Long Blue

This entity defines a long, blue vine using Noita's Verlet physics system. It's composed of multiple segments and simulates realistic swaying and interaction with the environment.

## VerletPhysicsComponent

This component governs the physics simulation of the vine.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `num_points`          | The number of points (segments) that make up the vine.                      |
| `stiffness`           | Controls how rigid the vine is. Higher values mean less bending.            |
| `velocity_dampening`  | Reduces the velocity of the vine points over time, simulating friction.     |
| `resting_distance`    | The ideal distance between adjacent points when the vine is not stretched.  |
| `pixelate_sprite_transforms` | Enables pixelation effects on the vine's sprite transformations.          |
| `follow_entity_transform` | If set to 1, the vine will follow the transform of another entity.          |
| `simulate_wind`       | Enables wind simulation for the vine.                                       |
| `wind_change_speed`   | Controls how quickly the wind's direction and strength can change.          |
| `simulate_gravity`    | Enables gravity simulation for the vine.                                    |

## Base Components

The vine is constructed from several smaller vine segments. The `Base` tags reference these individual parts.

```xml
<Base file="data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_1.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_2.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_3.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_4.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_5.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_6.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_7.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_8.xml" />
```
*Note: Some segments are repeated to create the desired length and appearance.*

## MoveToSurfaceOnCreateComponent

This component ensures the vine attaches itself to a surface when it's created.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `lookup_radius`           | The radius within which the component searches for a surface to attach to.  |
| `verlet_min_joint_distance` | The minimum distance between joints required for a successful attachment.   |
| `type`                    | Specifies the type of attachment, in this case, `VERLET_ROPE_TWO_JOINTS`.   |

## AudioComponent

This component handles the sound effects associated with the vine.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `file`      | The audio bank file containing the sound events. |
| `event_root`| The root path for the vine's collision events.  |