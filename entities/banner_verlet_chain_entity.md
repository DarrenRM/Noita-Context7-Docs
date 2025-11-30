---
title: Banner Verlet Chain Entity
category: entities
---

# Banner Verlet Chain Entity

This document describes the `banner.xml` entity, which defines a banner-like object using Noita's Verlet physics system. This entity is designed to simulate a hanging banner that reacts to physics and wind.

## Entity Definition

The core of the banner entity is defined by the `<Entity>` tag.

## Key Components

### VerletPhysicsComponent

This component is crucial for defining the physics behavior of the banner.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `stiffness`           | Controls how rigid the banner material is. Higher values mean less bending. |
| `num_points`          | The number of points used to simulate the banner's chain.                   |
| `velocity_dampening`  | Reduces the velocity of the banner points over time, simulating air resistance. |
| `resting_distance`    | The default distance between connected points when not under stress.        |
| `simulate_gravity`    | Enables or disables gravity's effect on the banner.                         |
| `wind_change_speed`   | Influences how quickly the wind's effect on the banner changes.             |
| `mass_min`            | The minimum mass assigned to individual points in the Verlet chain.         |
| `mass_max`            | The maximum mass assigned to individual points in the Verlet chain.         |

### Base Components

The banner's visual and physical structure is built by inheriting from several "part" entities. These define the individual segments of the banner.

*   `data/entities/verlet_chains/banner/parts/verlet_1.xml`
*   `data/entities/verlet_chains/banner/parts/verlet_2.xml`
*   `data/entities/verlet_chains/banner/parts/verlet_3.xml`
*   `data/entities/verlet_chains/banner/parts/verlet_4.xml`

These `Base` tags indicate that the entity inherits properties and potentially other components from the specified XML files, effectively constructing the banner from multiple connected segments.