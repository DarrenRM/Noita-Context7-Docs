---
title: Slime Tentacle Thin 01 Entity
category: entities
---

# Slime Tentacle Thin 01 Entity

This entity defines a thin slime tentacle segment, utilizing Verlet physics for its flexible movement. It inherits its core properties from `slime_tentacle_piece_thin.xml` and is composed of multiple instances of this base entity.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle.

| Attribute           | Value   | Description                                                              |
| :------------------ | :------ | :----------------------------------------------------------------------- |
| `stiffness`         | `1.25`  | Controls how rigid the tentacle segments are. Higher values mean less bend. |
| `num_points`        | `7`     | The number of points used in the Verlet chain simulation.                |
| `velocity_dampening`| `0.8`   | Reduces the velocity of the tentacle segments over time, simulating drag. |
| `resting_distance`  | `1.0`   | The preferred distance between adjacent points in the chain.             |

### Base Entity Inheritance

The tentacle is constructed by repeatedly inheriting from a base tentacle piece.

*   `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin.xml` (repeated 6 times)

This indicates that the `slime_tentacle_thin_01` entity is essentially a chain of 7 `slime_tentacle_piece_thin` entities linked together by the `VerletPhysicsComponent`.