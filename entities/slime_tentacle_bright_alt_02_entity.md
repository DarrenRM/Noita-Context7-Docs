---
title: Slime Tentacle Bright Alt 02 Entity
category: entities
---

# Slime Tentacle Bright Alt 02 Entity

This entity defines a specific variant of a slime tentacle, likely used for visual or gameplay purposes. It inherits its core functionality from other slime tentacle pieces and utilizes Verlet physics for its chain-like behavior.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle, making it behave like a flexible chain.

| Attribute           | Value   | Description                                                                 |
| :------------------ | :------ | :-------------------------------------------------------------------------- |
| `stiffness`         | `1.25`  | Controls how rigid the tentacle chain is. Higher values mean less flexibility. |
| `num_points`        | `6`     | The number of points (segments) that make up the Verlet chain.              |
| `velocity_dampening`| `0.8`   | Reduces the velocity of the points over time, simulating friction or drag.  |
| `resting_distance`  | `2.0`   | The ideal distance between adjacent points in the chain when at rest.       |

### Base Components

This entity is constructed by inheriting from multiple other entity files, effectively assembling the tentacle from pre-defined pieces.

| File Path                                                              | Description                                                              |
| :--------------------------------------------------------------------- | :----------------------------------------------------------------------- |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_bright_alt.xml` | Defines a standard bright slime tentacle segment. (Inherited 3 times)    |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin_alt.xml`   | Defines a thinner bright slime tentacle segment. (Inherited 2 times)     |

## Inheritance

The `InheritTransformComponent` is present but empty, indicating that this entity does not modify the transformation (position, rotation, scale) inherited from its parent or base entities.

---