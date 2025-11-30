---
title: Dark Long Blue Verlet Vine
category: entities
---

# Dark Long Blue Verlet Vine

This entity defines a long, dark blue vine using the Verlet physics system. It's composed of multiple segments and is designed to attach to surfaces.

## VerletPhysicsComponent

This component governs the physics simulation of the vine.

### Key Attributes:

*   `num_points`: The number of points (segments) that make up the Verlet chain. A higher number results in a more flexible and detailed chain.
    *   Value: `17`
*   `stiffness`: Controls how rigid the vine is. Higher values mean less stretching.
    *   Value: `1.0`
*   `velocity_dampening`: Reduces the velocity of the vine's points over time, helping it settle.
    *   Value: `0.9`
*   `resting_distance`: The ideal distance between adjacent points in the chain when no forces are applied.
    *   Value: `4`
*   `simulate_wind`: Enables wind simulation for the vine.
    *   Value: `1` (Enabled)
*   `simulate_gravity`: Enables gravity simulation for the vine.
    *   Value: `1` (Enabled)

## Base Components

The vine is constructed from several individual vine segments. The `Base` tag includes references to these segments, defining the visual appearance and collision properties of each part.

### Included Segments:

The following files define the individual parts of the vine. Note that some segments are repeated, which can affect the vine's appearance and physics behavior.

*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_3.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_4.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_5.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_8.xml`

*(Note: The list above includes all `Base` file references from the source. Some files are listed multiple times.)*

## MoveToSurfaceOnCreateComponent

This component ensures that when the vine is created, it attempts to attach itself to the nearest surface.

### Key Attributes:

*   `verlet_min_joint_distance`: The minimum distance between joints for the attachment to be considered valid.
    *   Value: `40`
*   `type`: Specifies the type of Verlet rope attachment.
    *   Value: `VERLET_ROPE_TWO_JOINTS`

## AudioComponent

This component handles the audio effects associated with the vine, specifically for collisions.

### Key Attributes:

*   `file`: The audio bank containing the sound events.
    *   Value: `data/audio/Desktop/materials.bank`
*   `event_root`: The root path for the audio events.
    *   Value: `collision/vine`