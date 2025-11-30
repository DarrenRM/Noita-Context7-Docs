---
title: Debug Verlet Vine 3
category: entities
---

# Debug Verlet Vine 3

This entity defines a debug version of a verlet vine, primarily for testing and development purposes. It utilizes the `VerletPhysicsComponent` to simulate the physics of a chain-like structure.

## VerletPhysicsComponent

This component governs the physics simulation of the verlet chain.

### Key Attributes:

*   **`num_points`**: The number of points (segments) in the verlet chain. A higher number results in a more detailed and flexible chain.
    *   Value: `15`
*   **`stiffness`**: Controls how rigid the chain is. A value of `1.0` indicates a relatively stiff chain. Lower values make it more flexible and prone to stretching.
    *   Value: `1.0`
*   **`velocity_dampening`**: Reduces the velocity of the chain's points over time, helping to stabilize the simulation and prevent excessive oscillation.
    *   Value: `0.9`
*   **`resting_distance`**: The ideal distance between adjacent points in the chain when no forces are applied.
    *   Value: `4`
*   **`simulate_wind`**: Enables or disables the simulation of wind forces acting on the chain.
    *   Value: `1` (Enabled)
*   **`wind_change_speed`**: Determines how quickly the wind direction and strength can change.
    *   Value: `0.25`
*   **`simulate_gravity`**: Enables or disables the simulation of gravity acting on the chain.
    *   Value: `1` (Enabled)

## Base Components

This entity inherits its visual and structural components from several other verlet vine part entities. This allows for the construction of a longer, more complex vine by combining pre-defined segments.

### Included Base Files:

*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_3.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_4.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_5.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_8.xml`

Note: Some vine part files are included multiple times, which may lead to a longer or more complex vine structure than intended for a standard vine. This is typical for debug entities.