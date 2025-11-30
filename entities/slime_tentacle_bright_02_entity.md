---
title: Slime Tentacle Bright 02 Entity
category: entities
---

# Slime Tentacle Bright 02 Entity

This entity defines a segment of a bright slime tentacle, utilizing Verlet physics for its chain-like behavior. It inherits its core properties from base tentacle piece entities.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle segment, allowing it to behave like a flexible chain.

| Attribute           | Value   | Description                                                                 |
| :------------------ | :------ | :-------------------------------------------------------------------------- |
| `stiffness`         | `1.25`  | Controls how rigid the tentacle chain is. Higher values mean less flexibility. |
| `num_points`        | `6`     | The number of points used to simulate the chain. More points allow for finer detail. |
| `velocity_dampening`| `0.8`   | Reduces the velocity of the points over time, simulating friction or air resistance. |
| `resting_distance`  | `2.0`   | The preferred distance between connected points in the chain when at rest.  |

### Base Components

This entity is constructed by inheriting from multiple base tentacle piece definitions. This allows for modularity and reuse of tentacle segment designs.

*   `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_bright.xml` (Inherited 3 times)
*   `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin.xml` (Inherited 2 times)

These inherited files likely define the visual appearance, collision properties, and other specific behaviors of the individual tentacle segments.