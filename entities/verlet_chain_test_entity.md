---
title: Verlet Chain Test Entity
category: entities
---

# Verlet Chain Test Entity

This entity is designed for testing the `VerletPhysicsComponent` in Noita. It creates a chain of connected "rope" entities to demonstrate Verlet physics simulation.

## Entity Structure

The entity primarily uses the `VerletPhysicsComponent` and inherits from multiple instances of a base "rope" entity.

### Key Components

*   **`VerletPhysicsComponent`**: This component enables Verlet physics simulation for the entity.
    *   `num_points`: The number of points in the simulated chain.
    *   `stiffness`: Controls the rigidity of the chain. Higher values mean a stiffer chain.
    *   `resting_distance`: The preferred distance between connected points.
    *   `simulate_wind`: Whether wind forces affect the chain (0 = off, 1 = on).
    *   `simulate_gravity`: Whether gravity affects the chain (0 = off, 1 = on).
*   **`DebugFollowMouseComponent`**: Allows the entity to be controlled by the mouse cursor for interactive testing.
*   **`Base`**: This tag is used to include other entity definitions. In this case, it repeatedly includes `data/entities/debug/rope.xml` and `data/entities/debug/rope2.xml` to form the chain.

### Included Base Entities

The entity is constructed by instantiating the following base entities multiple times:

*   `data/entities/debug/rope.xml` (included 11 times)
*   `data/entities/debug/rope2.xml` (included 1 time)

This setup allows for testing how multiple connected Verlet physics objects behave.