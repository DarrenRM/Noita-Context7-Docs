---
title: Slime Tentacle Thin Alt 01
category: entities
---

---

# Slime Tentacle Thin Alt 01

This entity defines a thin, alternative slime tentacle segment used in Noita's Verlet physics system. It inherits its core functionality from a base tentacle piece and is configured with specific physics properties.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle segment.

| Attribute             | Value   | Description                                                                 |
| :-------------------- | :------ | :-------------------------------------------------------------------------- |
| `stiffness`           | `1.25`  | Controls how rigid the tentacle is. Higher values mean less bending.        |
| `num_points`          | `7`     | The number of points used to simulate the tentacle's chain.                 |
| `velocity_dampening`  | `0.8`   | Reduces the velocity of the tentacle points over time, simulating friction. |
| `resting_distance`    | `1.0`   | The preferred distance between connected points in the chain.               |

### Base Entity Inheritance

The tentacle is constructed by repeatedly inheriting from a base entity.

| Inherited File                                           | Description                                                              |
| :------------------------------------------------------- | :----------------------------------------------------------------------- |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin_alt.xml` | This file likely defines the visual and basic properties of a single tentacle segment. |

The `Base` tag is repeated 6 times, indicating that this tentacle is composed of 6 connected segments, each inheriting from `slime_tentacle_piece_thin_alt.xml`.

## Other Components

### InheritTransformComponent

This component is present but empty, suggesting it might be a placeholder or intended for future use in inheriting transformation properties.