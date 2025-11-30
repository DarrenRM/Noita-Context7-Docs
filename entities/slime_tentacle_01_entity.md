---
title: Slime Tentacle 01 Entity
category: entities
---

# Slime Tentacle 01 Entity

This entity defines a segment of a slime tentacle, utilizing Verlet physics for its dynamic behavior. It inherits properties from a base tentacle piece and a thinner variant.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle segment.

| Attribute           | Value   | Description                                                                 |
| :------------------ | :------ | :-------------------------------------------------------------------------- |
| `stiffness`         | `1.25`  | Controls how rigid the tentacle segments are. Higher values mean less bend. |
| `num_points`        | `5`     | The number of points used to simulate the tentacle's physics chain.        |
| `velocity_dampening`| `0.8`   | Reduces the velocity of the tentacle points over time, simulating friction. |
| `resting_distance`  | `1.0`   | The preferred distance between connected points in the physics chain.       |

### Base Components

This entity is constructed by inheriting from other base entity files, allowing for modularity and reuse of tentacle segment definitions.

| File Path                                                | Description                               |
| :------------------------------------------------------- | :---------------------------------------- |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece.xml` | Defines a standard tentacle segment.      |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin.xml` | Defines a thinner variant of a tentacle segment. |