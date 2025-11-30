---
title: Slime Tentacle 03 Entity
category: entities
---

# Slime Tentacle 03 Entity

This entity defines a specific configuration for a slime tentacle, building upon a base `verlet_chain` structure. It's designed to create a segmented, flexible appendage.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle, making it behave like a chain of connected points.

| Attribute             | Value   | Description                                                              |
| :-------------------- | :------ | :----------------------------------------------------------------------- |
| `stiffness`           | `1.25`  | Controls how rigid the connections between points are. Higher values mean less flexibility. |
| `num_points`          | `8`     | The number of individual points that make up the Verlet chain.           |
| `velocity_dampening`  | `0.8`   | Reduces the velocity of points over time, simulating friction or air resistance. |
| `resting_distance`    | `2.0`   | The preferred distance between adjacent points when the chain is at rest. |

### Base Components

The entity inherits its visual and functional properties from several base entity files. This allows for modularity and reuse of tentacle segments.

| File Path                                              | Description                                                              |
| :----------------------------------------------------- | :----------------------------------------------------------------------- |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece.xml` | Defines a standard segment of the slime tentacle. This is inherited multiple times to form the main body. |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin.xml` | Defines a thinner segment of the slime tentacle. Used towards the end to taper the tentacle. |

## Inheritance Structure

The entity is constructed by inheriting from a common `verlet_chain` template and then layering specific segment types.

*   **`InheritTransformComponent`**: Present but empty, indicating it inherits transform properties from its parent or context.
*   **`VerletPhysicsComponent`**: Configured with specific physics parameters for this tentacle variant.
*   **`Base` files**: Multiple instances of `slime_tentacle_piece.xml` create the bulk of the tentacle, followed by `slime_tentacle_piece_thin.xml` to create a tapering effect.

This setup allows for easy modification of tentacle length, thickness, and physical properties by adjusting the number and type of inherited base components or the `VerletPhysicsComponent` parameters.