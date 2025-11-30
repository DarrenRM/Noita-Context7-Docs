---
title: Verlet Vine Shorter Blue
category: entities
---

# Verlet Vine Shorter Blue

This entity defines a shorter, blue variant of a verlet vine. It utilizes the `VerletPhysicsComponent` to simulate its chain-like behavior and `MoveToSurfaceOnCreateComponent` to attach itself to surfaces.

## VerletPhysicsComponent

This component governs the physics simulation of the verlet chain.

### Key Attributes:

*   **`num_points`**: `6` - The number of points (segments) in the verlet chain.
*   **`stiffness`**: `1.0` - Controls how rigid the chain is. Higher values mean less bending.
*   **`velocity_dampening`**: `0.9` - Reduces the velocity of the points each frame, simulating friction or air resistance.
*   **`resting_distance`**: `4` - The ideal distance between adjacent points when no forces are applied.
*   **`simulate_wind`**: `1` - Enables wind simulation for the vine.
*   **`wind_change_speed`**: `0.25` - Controls how quickly the wind direction and strength change.
*   **`simulate_gravity`**: `1` - Enables gravity simulation for the vine.

## Base Components

This entity is composed of several base vine parts, defining its visual appearance and structure.

### Included Base Files:

*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_8.xml`

## MoveToSurfaceOnCreateComponent

This component ensures the verlet vine attaches itself to a surface upon creation.

### Key Attributes:

*   **`lookup_radius`**: `20` - The radius within which to search for a surface to attach to.
*   **`verlet_min_joint_distance`**: `10` - The minimum distance between joints required for attachment.
*   **`type`**: `VERLET_ROPE_ONE_JOINT` - Specifies the type of attachment, indicating a single joint connection.

## AudioComponent

This component handles the audio events associated with the vine.

### Key Attributes:

*   **`file`**: `data/audio/Desktop/materials.bank` - The audio bank containing the sound effects.
*   **`event_root`**: `collision/vine` - The root event name for vine-related audio, likely used for collision sounds.