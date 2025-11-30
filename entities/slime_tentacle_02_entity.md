---
title: Slime Tentacle 02 Entity
category: entities
---

---

# Slime Tentacle 02 Entity

This entity defines a specific configuration of a slime tentacle, likely a variant with a particular visual or physical property. It inherits its core functionality from `slime_tentacle_piece.xml` and `slime_tentacle_piece_thin.xml`, suggesting it's composed of multiple segments.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle, making it behave like a chain of connected points.

| Attribute             | Value   | Description                                                                 |
| :-------------------- | :------ | :-------------------------------------------------------------------------- |
| `stiffness`           | `1.25`  | Controls how rigid the tentacle segments are. Higher values mean less bending. |
| `num_points`          | `6`     | The number of points (segments) that make up this tentacle.                 |
| `velocity_dampening`  | `0.8`   | Reduces the velocity of the tentacle segments over time, causing it to settle. |
| `resting_distance`    | `2.0`   | The preferred distance between connected points when the tentacle is at rest. |

### Base Components

This entity is constructed by inheriting from multiple base entity files, defining the individual segments of the tentacle.

| File Path                                             | Description                                     |
| :---------------------------------------------------- | :---------------------------------------------- |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece.xml` | Defines a standard tentacle segment.            |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin.xml` | Defines a thinner variant of a tentacle segment. |

The entity includes three instances of `slime_tentacle_piece.xml` and two instances of `slime_tentacle_piece_thin.xml`, suggesting a tentacle structure with a mix of standard and thinner segments.

## Inherited Components

### InheritTransformComponent

This component is present but empty, indicating that the entity inherits its transformation properties (position, rotation, scale) from its parent or the game engine's default behavior.