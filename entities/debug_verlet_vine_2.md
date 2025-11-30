---
title: Debug Verlet Vine 2
category: entities
---

# Debug Verlet Vine 2

This entity defines a debug vine using the Verlet physics system. It's designed to test and showcase the behavior of connected physics points.

## VerletPhysicsComponent

This component governs the physics simulation for the vine.

### Key Attributes:

*   **`num_points`**: The number of individual points that make up the Verlet chain. Higher numbers create more detailed and flexible chains.
    *   Value: `15`
*   **`stiffness`**: Controls how rigid the connections between points are. A value of `1.0` indicates a relatively stiff chain.
    *   Value: `1.0`
*   **`velocity_dampening`**: Reduces the velocity of points over time, helping to stabilize the simulation and prevent excessive bouncing.
    *   Value: `0.9`
*   **`resting_distance`**: The ideal distance between connected points when no forces are applied.
    *   Value: `4`
*   **`simulate_wind`**: Enables or disables the simulation of wind forces acting on the vine.
    *   Value: `1` (Enabled)
*   **`wind_change_speed`**: How quickly the wind direction and strength can change.
    *   Value: `0.25`
*   **`simulate_gravity`**: Enables or disables the simulation of gravity acting on the vine.
    *   Value: `1` (Enabled)

## Base Components

The vine is constructed by inheriting from several base vine part entities. This allows for modularity and reuse of vine segment designs.

### Included Base Files:

*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_3.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_4.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_5.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_8.xml`

*(Note: Some base files are listed multiple times, which may indicate redundancy or specific layering in the original design.)*

## MoveToSurfaceOnCreateComponent

This component ensures that when the vine is created, it attempts to attach itself to a nearby surface.

### Key Attributes:

*   **`verlet_min_joint_distance`**: The minimum distance a joint can be from a surface for the attachment to occur.
    *   Value: `16`
*   **`type`**: Specifies the type of attachment behavior. `VERLET_ROPE_ONE_JOINT` suggests it will try to attach with a single point.
    *   Value: `VERLET_ROPE_ONE_JOINT`