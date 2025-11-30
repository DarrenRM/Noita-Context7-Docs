---
title: Slime Tentacle Bright 01 Entity
category: entities
---

# Slime Tentacle Bright 01 Entity

This entity defines a segment of a bright slime tentacle, utilizing Verlet physics for its chain-like behavior. It inherits its visual and functional properties from base tentacle piece entities.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle segment, allowing it to behave like a flexible chain.

| Attribute           | Value   | Description                                                                 |
| :------------------ | :------ | :-------------------------------------------------------------------------- |
| `stiffness`         | `1.25`  | Controls how rigid the tentacle chain is. Higher values mean less flexibility. |
| `num_points`        | `5`     | The number of points used to simulate the Verlet chain.                     |
| `velocity_dampening`| `0.8`   | Reduces the velocity of the points over time, simulating friction or drag.  |
| `resting_distance`  | `1.0`   | The ideal distance between adjacent points in the chain when at rest.       |

### Base Components

The entity inherits its core properties from other base tentacle piece entities. This allows for modularity and reuse of tentacle segment designs.

*   `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_bright.xml` (Inherited 3 times)
*   `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin.xml` (Inherited 1 time)

These base files likely define the visual appearance, collision properties, and any specific behaviors of the individual tentacle segments.