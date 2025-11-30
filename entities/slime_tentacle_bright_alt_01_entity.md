---
title: Slime Tentacle Bright Alt 01 Entity
category: entities
---

# Slime Tentacle Bright Alt 01 Entity

This entity defines a specific variant of a slime tentacle, characterized by its bright, alternative appearance. It utilizes a `VerletPhysicsComponent` to simulate the chain-like physics of the tentacle.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle.

| Attribute           | Value   | Description                                                                 |
| :------------------ | :------ | :-------------------------------------------------------------------------- |
| `stiffness`         | `1.25`  | Controls how rigid the tentacle segments are. Higher values mean less bend. |
| `num_points`        | `5`     | The number of points (segments) that make up the tentacle's physics chain.  |
| `velocity_dampening`| `0.8`   | Reduces the velocity of the tentacle segments over time, simulating friction. |
| `resting_distance`  | `1.0`   | The ideal distance between adjacent points in the physics chain.            |

### Base Components

This entity inherits its visual and functional properties from other base entities, creating the tentacle's structure.

| File Path                                                              | Description                                                                                             |
| :--------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_bright_alt.xml` | Defines a standard bright, alternative slime tentacle segment. This is inherited multiple times.        |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin_alt.xml`   | Defines a thinner, bright, alternative slime tentacle segment. This adds variation to the tentacle's form. |

## InheritTransformComponent

This component is present but empty, indicating that it inherits its transform properties from its parent entity without any specific modifications within this file.