---
title: Slime Tentacle Alt 01 Entity
category: entities
---

# Slime Tentacle Alt 01 Entity

This entity defines an alternative variant of the slime tentacle, likely used for visual or behavioral variations. It inherits its core functionality from `slime_tentacle_piece_alt.xml` and `slime_tentacle_piece_thin_alt.xml`, suggesting it's composed of multiple segments.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle, allowing it to behave like a flexible chain.

| Attribute             | Value   | Description                                                              |
| :-------------------- | :------ | :----------------------------------------------------------------------- |
| `stiffness`           | `1.25`  | Controls how rigid the tentacle segments are. Higher values mean less bend. |
| `num_points`          | `5`     | The number of points (segments) that make up the Verlet chain.           |
| `velocity_dampening`  | `0.8`   | Reduces the velocity of the tentacle segments over time, causing it to settle. |
| `resting_distance`    | `1.0`   | The preferred distance between adjacent points in the chain when at rest. |

### Base Components

This entity is constructed by inheriting from other base entity files, defining the visual and functional properties of its segments.

| File Path                                                     | Description                                                              |
| :------------------------------------------------------------ | :----------------------------------------------------------------------- |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_alt.xml` | Defines a standard segment for the alternative slime tentacle.           |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin_alt.xml` | Defines a thinner segment for the alternative slime tentacle.            |