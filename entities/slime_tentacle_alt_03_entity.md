---
title: Slime Tentacle Alt 03 Entity
category: entities
---

# Slime Tentacle Alt 03 Entity

This entity defines an alternative variant of the slime tentacle, likely used for visual or behavioral variations. It inherits its core functionality from base tentacle pieces and utilizes Verlet physics for its chain-like movement.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle's chain.

| Attribute           | Value   | Description                                                                 |
| :------------------ | :------ | :-------------------------------------------------------------------------- |
| `stiffness`         | `1.25`  | Controls how rigid the tentacle segments are. Higher values mean less bending. |
| `num_points`        | `8`     | The number of points (segments) that make up the Verlet chain.              |
| `velocity_dampening`| `0.8`   | Reduces the velocity of the tentacle segments over time, simulating drag.   |
| `resting_distance`  | `2.0`   | The preferred distance between adjacent points in the chain when at rest.   |

### Base Components

This entity reuses existing tentacle piece definitions to construct the tentacle.

| File Path                                                | Description                                                              |
| :------------------------------------------------------- | :----------------------------------------------------------------------- |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_alt.xml` | Defines a standard segment for the alternative slime tentacle. (Repeated 5 times) |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin_alt.xml` | Defines a thinner segment for the alternative slime tentacle. (Repeated 2 times) |