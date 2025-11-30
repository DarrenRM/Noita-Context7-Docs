---
title: Verlet Vine Dark Short Blue
category: entities
---

# Verlet Vine Dark Short Blue

This entity defines a short, dark blue vine using the Verlet physics system. It's designed to attach to surfaces and sway realistically.

## VerletPhysicsComponent

This component governs the physics simulation of the vine.

### Key Attributes:

*   `num_points`: The number of segments the vine is divided into for physics simulation.
    *   Value: `8`
*   `stiffness`: Controls how rigid the vine segments are. Higher values mean less bending.
    *   Value: `1.0`
*   `velocity_dampening`: Reduces the velocity of the vine segments over time, causing it to settle.
    *   Value: `0.9`
*   `resting_distance`: The preferred distance between adjacent points when the vine is at rest.
    *   Value: `4`
*   `simulate_wind`: Enables wind simulation for the vine.
    *   Value: `1` (True)
*   `wind_change_speed`: How quickly the wind's direction and strength can change.
    *   Value: `0.25`
*   `simulate_gravity`: Enables gravity simulation for the vine.
    *   Value: `1` (True)

## Base Components

These components define the visual appearance and structure of the vine by referencing individual vine segments.

### Included Vine Segments:

*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_3.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_5.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_verlet_b_8.xml`

## MoveToSurfaceOnCreateComponent

This component ensures the vine attaches itself to the nearest surface upon creation.

### Key Attributes:

*   `lookup_radius`: The area around the vine's spawn point to search for a surface.
    *   Value: `28`
*   `verlet_min_joint_distance`: The minimum distance between joints that the vine will try to maintain when attaching.
    *   Value: `14`
*   `type`: Specifies the attachment behavior.
    *   Value: `VERLET_ROPE_ONE_JOINT` (Indicates it will attach with a single joint)

## AudioComponent

This component handles the sound effects associated with the vine.

### Key Attributes:

*   `file`: The audio bank containing the sound events.
    *   Value: `data/audio/Desktop/materials.bank`
*   `event_root`: The base name for sound events related to this vine.
    *   Value: `collision/vine`