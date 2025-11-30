---
title: Meatvine Shorter Verlet Chain
category: entities
---

# Meatvine Shorter Verlet Chain

This entity defines a shorter, more compact version of the meatvine's verlet chain, used for its physical simulation and appearance.

## VerletPhysicsComponent

This component governs the physics simulation of the verlet chain.

### Key Attributes:

*   **num_points**: `6` - The number of points in the verlet chain.
*   **stiffness**: `1.0` - Controls how rigid the chain is. Higher values mean less bending.
*   **velocity_dampening**: `0.9` - Reduces the velocity of the chain over time, making it settle.
*   **resting_distance**: `4` - The ideal distance between adjacent points in the chain.
*   **simulate_wind**: `1` - Enables simulation of wind forces affecting the chain.
*   **wind_change_speed**: `0.25` - Controls how quickly wind direction and strength change.
*   **simulate_gravity**: `1` - Enables simulation of gravity affecting the chain.

## Base Components

This entity utilizes several `Base` components to define the visual segments of the verlet chain. These likely refer to different visual parts of the vine.

### Included Base Files:

*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_1.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_2.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_6.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_7.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_8.xml`

## MoveToSurfaceOnCreateComponent

This component ensures the verlet chain attaches to a surface upon creation.

### Key Attributes:

*   **lookup_radius**: `20` - The radius within which to search for a surface to attach to.
*   **verlet_min_joint_distance**: `10` - The minimum distance required between joints for attachment.
*   **type**: `VERLET_ROPE_ONE_JOINT` - Specifies the type of verlet rope attachment.

## AudioComponent

This component handles audio events related to the verlet chain, specifically for collisions.

### Key Attributes:

*   **file**: `data/audio/Desktop/materials.bank` - The audio bank containing the sound events.
*   **event_root**: `collision/vine` - The root event name for vine collision sounds.