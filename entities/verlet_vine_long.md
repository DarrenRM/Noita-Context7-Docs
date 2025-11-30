---
title: Verlet Vine Long
category: entities
---

# Verlet Vine Long

This entity defines a long, flexible vine-like structure using Noita's Verlet physics system. It's designed to simulate organic growth and movement, likely for environmental elements or enemy parts.

## VerletPhysicsComponent

This component governs the physical behavior of the vine.

*   **num_points**: `17` - The number of segments or points that make up the vine's physics chain. More points generally lead to smoother, more detailed movement.
*   **stiffness**: `1.0` - Controls how rigid the vine is. A value of 1.0 suggests a relatively stiff but still flexible vine.
*   **velocity\_dampening**: `0.9` - Reduces the velocity of the vine's points over time, helping it settle and preventing excessive oscillation.
*   **resting\_distance**: `4` - The ideal distance between adjacent points when the vine is not under stress.
*   **simulate\_wind**: `1` - Enables the simulation of wind forces acting on the vine.
*   **wind\_change\_speed**: `0.25` - How quickly wind direction and strength can change.
*   **simulate\_gravity**: `1` - Enables the simulation of gravity acting on the vine.

## Base Components

The vine is constructed from multiple instances of pre-defined vine segments. The `Base` tag indicates that these segments are loaded from other entity files.

*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_1.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_2.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_3.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_4.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_5.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_6.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_7.xml`
*   `data/entities/verlet_chains/meatvine/vine_parts/vine_verlet_b_8.xml`

*(Note: Some vine parts are repeated in the XML, which might be intentional for specific visual or physical effects, or could be a remnant of development.)*

## MoveToSurfaceOnCreateComponent

This component dictates how the vine attaches itself upon creation.

*   **lookup\_radius**: `64` - The area around the entity's spawn point to search for a surface to attach to.
*   **verlet\_min\_joint\_distance**: `40` - The minimum distance between two attachment points on the vine to the surface.
*   **type**: `VERLET_ROPE_TWO_JOINTS` - Specifies that the vine should attach as a rope with two connection points.

## AudioComponent

This component handles sound effects associated with the vine.

*   **file**: `data/audio/Desktop/materials.bank` - The audio bank containing the sound events.
*   **event\_root**: `collision/vine` - The root event name for vine-related sounds, likely triggered by collisions.