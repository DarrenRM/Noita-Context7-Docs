---
title: Dark Blue Verlet Vine
category: entities
---

# Dark Blue Verlet Vine

This document details the configuration for a dark blue vine entity in Noita, utilizing the Verlet physics system.

## Entity Structure

The `verlet_vine_dark_blue.xml` file defines a single entity with several key components that govern its appearance, physics, and behavior.

```xml
<Entity >
    <!-- VerletPhysicsComponent -->
    <!-- Base entities -->
    <!-- MoveToSurfaceOnCreateComponent -->
    <!-- AudioComponent -->
</Entity>
```

## VerletPhysicsComponent

This component is central to the vine's dynamic behavior, simulating a chain of connected points with physical properties.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `num_points`          | The number of points in the Verlet chain, defining its length and flexibility. |
| `stiffness`           | Controls how rigid the vine is. Higher values mean less bending.            |
| `velocity_dampening`  | Reduces the velocity of points over time, simulating friction or air resistance. |
| `resting_distance`    | The ideal distance between adjacent points when the vine is not under tension. |
| `pixelate_sprite_transforms` | Enables pixelation effects on the sprite as it deforms.                   |
| `follow_entity_transform` | If set to 1, the entire chain would follow a parent entity's transform.     |
| `simulate_wind`       | Enables the simulation of wind affecting the vine.                          |
| `wind_change_speed`   | Controls how quickly wind direction and strength can change.                |
| `simulate_gravity`    | Enables gravity to affect the vine's points.                                |

## Base Entities

The vine is constructed from multiple smaller entities, each representing a segment of the vine. These are loaded using the `<Base>` tag.

| File Path                                                              | Description                                                              |
| :--------------------------------------------------------------------- | :----------------------------------------------------------------------- |
| `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_1.xml` | Defines the first segment of the dark blue vine.                         |
| `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_2.xml` | Defines the second segment of the dark blue vine.                        |
| `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_3.xml` | Defines the third segment of the dark blue vine.                         |
| `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_4.xml` | Defines the fourth segment of the dark blue vine.                        |
| `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_5.xml` | Defines the fifth segment of the dark blue vine.                         |
| `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_6.xml` | Defines the sixth segment of the dark blue vine.                         |
| `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_7.xml` | Defines the seventh segment of the dark blue vine.                       |
| `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_8.xml` | Defines the eighth segment of the dark blue vine.                        |

*Note: The list of base entities appears to have some duplication, which might be intentional for creating a longer or more complex vine structure.*

## MoveToSurfaceOnCreateComponent

This component dictates how the vine attaches itself upon creation.

| Attribute                 | Description                                                                                             |
| :------------------------ | :------------------------------------------------------------------------------------------------------ |
| `verlet_min_joint_distance` | The minimum distance between joints required for the vine to successfully attach to a surface.           |
| `type`                    | Specifies the type of attachment behavior. `VERLET_ROPE_TWO_JOINTS` suggests it will anchor at two points. |

## AudioComponent

This component handles the sound effects associated with the vine.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `file`      | The audio bank file containing the sound events.                         |
| `event_root` | The root path for sound events within the bank, specifically for vine collisions. |