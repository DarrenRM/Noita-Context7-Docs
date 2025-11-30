---
title: Debug Verlet Vine Entity
category: entities
---

# Debug Verlet Vine Entity

This entity defines a debug version of a verlet vine, primarily for testing and development purposes. It utilizes the `VerletPhysicsComponent` to simulate a chain of connected points, mimicking the behavior of a vine.

## VerletPhysicsComponent

This component governs the physics simulation of the verlet chain.

### Key Attributes:

*   **`num_points`**: The number of points in the verlet chain. Higher values result in a more detailed and flexible chain.
    *   **Value**: `15`
*   **`stiffness`**: Controls how rigid the chain is. A value of `1.0` indicates a relatively stiff chain.
    *   **Value**: `1.0`
*   **`velocity_dampening`**: Reduces the velocity of the points in the chain over time, helping to stabilize the simulation.
    *   **Value**: `0.9`
*   **`resting_distance`**: The ideal distance between adjacent points when the chain is not under stress.
    *   **Value**: `4`
*   **`simulate_wind`**: Enables or disables wind simulation affecting the chain.
    *   **Value**: `1` (Enabled)
*   **`wind_change_speed`**: Controls how quickly the wind's direction and intensity change.
    *   **Value**: `0.25`
*   **`simulate_gravity`**: Enables or disables gravity simulation affecting the chain.
    *   **Value**: `1` (Enabled)

## Base Components

This entity includes multiple `<Base>` components, each referencing a different part of the vine. These are likely used to construct the visual appearance and potentially the collision properties of the vine by combining various pre-defined vine segments.

### Referenced Files:

*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_3.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_4.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_5.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_8.xml`

*(Note: Some vine parts are listed multiple times, which might be for creating longer or more complex vine structures.)*

## MoveToSurfaceOnCreateComponent

This component dictates how the verlet chain interacts with surfaces upon its creation.

### Key Attributes:

*   **`verlet_min_joint_distance`**: The minimum distance between joints that the verlet chain will attempt to maintain when moving to a surface.
    *   **Value**: `16`
*   **`type`**: Specifies the type of verlet rope behavior. `VERLET_ROPE_TWO_JOINTS` suggests a rope-like behavior with two primary attachment points.
    *   **Value**: `VERLET_ROPE_TWO_JOINTS`