---
title: Verlet Vine Shorter
category: entities
---

# Verlet Vine Shorter

This entity defines a shorter, more compact vine using the Verlet physics system. It's designed to be a flexible, hanging element that can sway and interact with the environment.

## VerletPhysicsComponent

This component governs the physics simulation of the vine.

### Key Attributes:

*   `num_points`: The number of segments the vine is broken into for physics simulation. A lower number results in a stiffer, less detailed chain.
    *   **Value:** `6`
*   `stiffness`: Controls how much the segments resist stretching. Higher values make the vine more rigid.
    *   **Value:** `1.0`
*   `velocity_dampening`: Reduces the velocity of the vine segments over time, causing it to settle.
    *   **Value:** `0.9`
*   `resting_distance`: The ideal distance between adjacent points when the vine is not under tension.
    *   **Value:** `4`
*   `simulate_wind`: Enables wind simulation for the vine.
    *   **Value:** `1` (enabled)
*   `wind_change_speed`: How quickly the wind's direction and intensity can change.
    *   **Value:** `0.25`
*   `simulate_gravity`: Enables gravity simulation for the vine.
    *   **Value:** `1` (enabled)

## Base Components

This entity utilizes several `Base` components to define the visual appearance and structure of the vine. These likely refer to different visual segments of the vine.

### Included Base Files:

*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_b_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_b_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_b_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_b_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_b_8.xml`

## MoveToSurfaceOnCreateComponent

This component ensures that when the vine is created, it attempts to attach itself to a nearby surface.

### Key Attributes:

*   `lookup_radius`: The area around the vine's creation point to search for a surface.
    *   **Value:** `20`
*   `verlet_min_joint_distance`: The minimum distance between joints when attaching to a surface.
    *   **Value:** `10`
*   `type`: Specifies the attachment behavior. `VERLET_ROPE_ONE_JOINT` suggests it will attach with a single point.
    *   **Value:** `VERLET_ROPE_ONE_JOINT`

## AudioComponent

This component handles sound effects associated with the vine.

### Key Attributes:

*   `file`: The audio bank containing the sound events.
    *   **Value:** `data/audio/Desktop/materials.bank`
*   `event_root`: The base name for sound events related to this entity.
    *   **Value:** `collision/vine`