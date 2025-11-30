---
title: Slime Tentacle Alt 02 Entity
category: entities
---

# Slime Tentacle Alt 02 Entity

This entity defines an alternative variant of the slime tentacle, likely used for visual or behavioral variations. It inherits its core functionality from other slime tentacle pieces and utilizes Verlet physics for its chain-like movement.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle, making it behave like a flexible chain.

| Attribute           | Value   | Description                                                                 |
| :------------------ | :------ | :-------------------------------------------------------------------------- |
| `stiffness`         | `1.25`  | Controls how rigid the tentacle chain is. Higher values mean less bending. |
| `num_points`        | `6`     | The number of segments or points that make up the Verlet chain.             |
| `velocity_dampening`| `0.8`   | Reduces the velocity of the tentacle segments over time, causing it to settle. |
| `resting_distance`  | `2.0`   | The ideal distance between adjacent points in the chain when not under stress. |

### Base Components

This entity reuses existing slime tentacle piece definitions to construct its appearance and behavior.

| File Path                                                     | Description                                                              |
| :------------------------------------------------------------ | :----------------------------------------------------------------------- |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_alt.xml` | Defines a standard alternative slime tentacle segment.                   |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin_alt.xml` | Defines a thinner alternative slime tentacle segment, likely for variation. |

The entity includes multiple instances of `slime_tentacle_piece_alt.xml` and `slime_tentacle_piece_thin_alt.xml`, suggesting a layered or varied structure for this specific tentacle variant.