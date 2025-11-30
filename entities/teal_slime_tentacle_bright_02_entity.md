---
title: Teal Slime Tentacle Bright 02 Entity
category: entities
---

# Teal Slime Tentacle Bright 02 Entity

This entity defines a segment of a teal slime tentacle, specifically a "bright" variant. It inherits its core functionality from other tentacle pieces and utilizes Verlet physics for its movement.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle segment, allowing it to behave like a chain of connected points.

*   **stiffness**: `1.25` - Controls how rigid the tentacle segment is. Higher values mean less bending.
*   **num_points**: `6` - The number of points used in the Verlet simulation for this segment. More points allow for more detailed and fluid movement.
*   **velocity_dampening**: `0.8` - Reduces the velocity of the points over time, simulating friction or air resistance.
*   **resting_distance**: `2.0` - The preferred distance between connected points when the tentacle is at rest.

### Base Components

This entity inherits its visual and functional properties from other tentacle piece entities.

*   **`data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece_bright.xml`**: This file is included multiple times, suggesting it defines the primary visual and physical characteristics of the bright tentacle segments.
*   **`data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece_thin.xml`**: This file is included, indicating that thinner segments are also part of this tentacle variant.

## Summary

The `tealslime_tentacle_bright_02.xml` entity is a building block for a larger teal slime tentacle. It leverages Verlet physics to create a flexible and dynamic chain-like structure, with its appearance and behavior influenced by inherited tentacle piece definitions. The specific configuration of `stiffness`, `num_points`, and `resting_distance` in the `VerletPhysicsComponent` dictates how this particular segment will move and interact within the game world.