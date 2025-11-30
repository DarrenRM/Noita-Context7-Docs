---
title: Dark Shorter Blue Verlet Vine
category: entities
---

# Dark Shorter Blue Verlet Vine

This entity defines a segment of a dark blue, shorter verlet vine. It utilizes the `VerletPhysicsComponent` to simulate its physical behavior and `MoveToSurfaceOnCreateComponent` to attach itself to surfaces.

## VerletPhysicsComponent

This component governs the physics simulation of the vine.

### Key Attributes:

*   `num_points`: The number of points used to simulate the vine's physics.
    *   Value: `6`
*   `stiffness`: Controls how rigid the vine is. Higher values mean less bending.
    *   Value: `1.0`
*   `velocity_dampening`: Reduces the velocity of the vine's points over time, simulating air resistance or friction.
    *   Value: `0.9`
*   `resting_distance`: The ideal distance between adjacent points when the vine is not under tension.
    *   Value: `4`
*   `simulate_wind`: Enables or disables wind simulation for the vine.
    *   Value: `1` (Enabled)
*   `wind_change_speed`: Controls how quickly the wind's direction and strength change.
    *   Value: `0.25`
*   `simulate_gravity`: Enables or disables gravity simulation for the vine.
    *   Value: `1` (Enabled)

## Base Components

This entity is composed of several base vine parts, defining its visual appearance and structure.

### Included Base Files:

*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_8.xml`

## MoveToSurfaceOnCreateComponent

This component ensures the vine attaches itself to a surface when created.

### Key Attributes:

*   `lookup_radius`: The radius within which the component searches for a surface to attach to.
    *   Value: `20`
*   `verlet_min_joint_distance`: The minimum distance between joints when attaching to a surface.
    *   Value: `10`
*   `type`: Specifies the type of attachment.
    *   Value: `VERLET_ROPE_ONE_JOINT`

## AudioComponent

This component handles the audio events associated with the vine, specifically for collisions.

### Key Attributes:

*   `file`: The audio bank file containing the sound events.
    *   Value: `data/audio/Desktop/materials.bank`
*   `event_root`: The root path for the audio events.
    *   Value: `collision/vine`