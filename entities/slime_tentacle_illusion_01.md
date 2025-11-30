---
title: Slime Tentacle Illusion 01
category: entities
---

# Slime Tentacle Illusion 01

This entity defines a segment of an illusory slime tentacle, likely used for visual effects or non-damaging environmental elements. It inherits its core functionality from `slime_tentacle_piece.xml` and `slime_tentacle_piece_thin.xml`, with a reduced alpha for a more ethereal appearance.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle segment, allowing it to behave like a chain of connected points.

| Attribute           | Value   | Description                                    |
| :------------------ | :------ | :--------------------------------------------- |
| `stiffness`         | `1.25`  | Controls how rigid the tentacle segments are.  |
| `num_points`        | `5`     | The number of points simulating the chain.     |
| `velocity_dampening`| `0.8`   | Reduces the velocity of the points over time.  |
| `resting_distance`  | `1.0`   | The preferred distance between connected points. |

### Base Components

The entity reuses existing tentacle piece definitions to construct its visual and physical form.

| File Path                                                | Description                                                              |
| :------------------------------------------------------- | :----------------------------------------------------------------------- |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece.xml` | Defines a standard tentacle segment.                                     |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin.xml` | Defines a thinner variant of a tentacle segment.                         |

### SpriteComponent (Inherited)

Each inherited `Base` component includes a `SpriteComponent` with an `alpha` value of `0.5`. This makes the tentacle segments semi-transparent, contributing to its "illusion" nature.