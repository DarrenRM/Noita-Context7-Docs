---
title: Teal Slime Tentacle 02 Entity
category: entities
---

# Teal Slime Tentacle 02 Entity

This entity defines a segment of a teal slime tentacle, utilizing Verlet physics for its chain-like behavior. It inherits its core properties from `tealslime_tentacle_piece.xml` and `tealslime_tentacle_piece_thin.xml`, creating a segmented, flexible structure.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle segments, allowing them to bend and sway realistically.

| Attribute           | Value   | Description                                                                 |
| :------------------ | :------ | :-------------------------------------------------------------------------- |
| `stiffness`         | `1.25`  | Controls how rigid the tentacle segments are. Higher values mean less bending. |
| `num_points`        | `6`     | The number of points used to simulate the physics chain.                    |
| `velocity_dampening`| `0.8`   | Reduces the velocity of the points over time, simulating friction/drag.     |
| `resting_distance`  | `2.0`   | The preferred distance between points in the physics chain.                 |

### Base Components

This entity is constructed by inheriting from multiple base entity files, defining the visual and functional aspects of the tentacle pieces.

*   `data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece.xml` (x3)
*   `data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece_thin.xml` (x2)

These base files likely define the sprite, collision, and other specific behaviors for each segment of the tentacle.

## Inheritance

The `InheritTransformComponent` is present but empty, indicating that this entity does not override any specific transform properties from its parent or base entities.