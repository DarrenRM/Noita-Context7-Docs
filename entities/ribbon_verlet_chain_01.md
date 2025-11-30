---
title: Ribbon Verlet Chain 01
category: entities
---

# Ribbon Verlet Chain 01

This document describes the configuration for a basic ribbon-likeverlet chain entity in Noita, designed for AI-assisted modding.

## Entity Configuration

The `ribbon_01.xml` file defines a simpleverlet chain with specific physics properties.

### VerletPhysicsComponent

This component governs the physics simulation of the ribbon.

| Attribute           | Value   | Description                                                                 |
| :------------------ | :------ | :-------------------------------------------------------------------------- |
| `stiffness`         | `1.9`   | Controls how rigid the chain segments are. Higher values mean less bending. |
| `num_points`        | `7`     | The number of points (segments) that make up the ribbon.                    |
| `velocity_dampening`| `0.85`  | Reduces the velocity of the points over time, simulating air resistance.    |
| `resting_distance`  | `3.5`   | The ideal distance between adjacent points when not under tension.          |
| `simulate_gravity`  | `1`     | Enables gravity simulation for the ribbon points.                           |
| `wind_change_speed` | `1.789` | Controls how quickly wind forces can change the ribbon's behavior.          |
| `mass_min`          | `0.12`  | The minimum mass assigned to each point in the chain.                       |
| `mass_max`          | `0.15`  | The maximum mass assigned to each point in the chain.                       |

### InheritTransformComponent

This component is present but empty, indicating it inherits transform properties from its parent or environment.

### Base Components

The ribbon is constructed by inheriting from a baseverlet chain part multiple times.

```xml
<Base file="data/entities/verlet_chains/ribbon/parts/verlet_1.xml" />
```

This line is repeated 6 times, meaning the ribbon is composed of 7 segments, each using the `verlet_1.xml` part definition. This part likely defines the visual sprite and collision properties for each segment.