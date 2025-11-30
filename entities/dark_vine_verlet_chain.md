---
title: Dark Vine Verlet Chain
category: entities
---

# Dark Vine Verlet Chain

This entity defines a dark-colored vine using the Verlet physics system. It's composed of multiple segments that simulate a flexible, hanging chain.

## VerletPhysicsComponent

This component governs the physics simulation of the vine.

### Key Attributes:

*   **num_points**: `15` - The number of points (segments) that make up the Verlet chain. More points result in a more detailed and flexible chain.
*   **stiffness**: `1.0` - Controls how rigid the vine is. A value of 1.0 means it's quite stiff. Lower values make it more flexible.
*   **velocity_dampening**: `0.9` - Reduces the velocity of the points each frame, helping to stabilize the simulation and prevent excessive oscillation.
*   **resting_distance**: `4` - The ideal distance between adjacent points when no forces are applied.
*   **simulate_wind**: `1` - Enables simulation of wind forces acting on the vine.
*   **wind_change_speed**: `0.25` - Controls how quickly wind direction and strength can change.
*   **simulate_gravity**: `1` - Enables simulation of gravity acting on the vine.

## Base Components

The vine is constructed from multiple `Base` entities, which likely define the visual appearance and collision properties of individual vine segments.

### Included Vine Parts:

*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_3.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_4.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_5.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_8.xml`

*(Note: Some vine parts are listed multiple times, which might be intentional for density or a potential redundancy.)*

## MoveToSurfaceOnCreateComponent

This component ensures that when the vine is created, it attempts to attach itself to a surface.

### Key Attributes:

*   **verlet_min_joint_distance**: `28` - The minimum distance between joints for the `VERLET_ROPE_TWO_JOINTS` type to be considered for surface attachment.
*   **type**: `VERLET_ROPE_TWO_JOINTS` - Specifies the type of Verlet rope behavior for surface attachment.

## AudioComponent

This component handles audio events related to the vine.

### Key Attributes:

*   **file**: `data/audio/Desktop/materials.bank` - The audio bank containing the sound effects.
*   **event_root**: `collision/vine` - The root event name for vine-related audio, likely used for collision sounds.