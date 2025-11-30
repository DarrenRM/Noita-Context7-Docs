---
title: Teal Slime Tentacle Segment
category: entities
---

# Teal Slime Tentacle Segment

This entity defines a segment of a teal slime tentacle, utilizing Verlet physics for its chain-like behavior. It inherits its core properties from a base tentacle piece and can be extended with variations.

## Key Components

### VerletPhysicsComponent
This component governs the physics simulation of the tentacle segment, allowing it to behave like a flexible chain.

*   **stiffness**: `1.25` - Controls how rigid the tentacle segment is. Higher values mean less bending.
*   **num_points**: `5` - The number of points used to simulate the physics chain. More points allow for more detailed bending.
*   **velocity\_dampening**: `0.8` - Reduces the velocity of the points over time, simulating air resistance or friction.
*   **resting\_distance**: `1.0` - The preferred distance between points in the chain when no forces are applied.

### Base Components
These elements define the visual and functional aspects of the tentacle segment by inheriting from other entity files.

*   **Base file**: `data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece.xml`
    *   This is the primary base for the tentacle segment, likely defining its visual appearance and basic behavior. It is inherited multiple times to form the chain.
*   **Base file**: `data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece_thin.xml`
    *   This base file is likely used for a thinner or different type of tentacle piece, potentially at the end of the chain or for variation.

## Inheritance

The `tealslime_tentacle_01.xml` file primarily acts as a container and configurator for a chain of tentacle segments. It inherits its core physics and visual properties from `tealslime_tentacle_piece.xml` and `tealslime_tentacle_piece_thin.xml`. The `VerletPhysicsComponent` is configured here to dictate the overall behavior of the entire chain.