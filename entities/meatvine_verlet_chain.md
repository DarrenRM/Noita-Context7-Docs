---
title: Meatvine Verlet Chain
category: entities
---

# Meatvine Verlet Chain

This document describes the `verlet_vine.xml` entity, which defines a meatvine segment used in Noita. It utilizes the Verlet physics system to simulate a flexible chain.

## VerletPhysicsComponent

This component governs the physical behavior of the verlet chain.

### Key Attributes:

*   **`num_points`**: The number of points (segments) that make up the verlet chain. Higher values result in a more detailed and flexible chain.
    *   Value: `15`
*   **`stiffness`**: Controls how rigid the chain is. A higher value means less bending.
    *   Value: `1.0`
*   **`velocity_dampening`**: Reduces the velocity of the points over time, preventing excessive oscillation.
    *   Value: `0.9`
*   **`resting_distance`**: The preferred distance between adjacent points when the chain is relaxed.
    *   Value: `4`
*   **`simulate_wind`**: Enables or disables wind simulation for the chain.
    *   Value: `1` (Enabled)
*   **`wind_change_speed`**: Controls how quickly the wind direction and intensity can change.
    *   Value: `0.25`
*   **`simulate_gravity`**: Enables or disables gravity simulation for the chain.
    *   Value: `1` (Enabled)

## Base Components

The meatvine is constructed from multiple `vine_verlet_b` parts. These are loaded sequentially to form the complete chain.

### Included Parts:

*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_1.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_2.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_3.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_4.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_5.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_6.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_7.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_8.xml`

*(Note: Some parts are listed multiple times, which may indicate intended repetition or a potential area for optimization in modding.)*

## MoveToSurfaceOnCreateComponent

This component ensures that the verlet chain attaches itself to a surface upon creation.

### Key Attributes:

*   **`verlet_min_joint_distance`**: The minimum distance between verlet joints required for the component to attempt attachment.
    *   Value: `28`
*   **`type`**: Specifies the type of verlet rope behavior.
    *   Value: `VERLET_ROPE_TWO_JOINTS`

## AudioComponent

This component handles the audio events associated with the meatvine.

### Key Attributes:

*   **`file`**: The audio bank file containing the sound events.
    *   Value: `data/audio/Desktop/materials.bank`
*   **`event_root`**: The root path for the audio events related to this entity.
    *   Value: `collision/vine`