---
title: Verlet Tail Entity
category: entities
---

# Verlet Tail Entity

This document describes the `verlet_tail.xml` entity, which defines a flexible, chain-like tail using Noita's Verlet physics system. This entity is designed to be attached to other entities and simulate a dynamic, trailing appendage.

## Core Components

### `InheritTransformComponent`

This component allows the tail to inherit its position and orientation from a parent entity.

*   **`parent_hotspot_tag`**: Specifies the tag of the hotspot on the parent entity to which this tail will attach. In this case, it's `"belt_root"`.
*   **`Transform`**: Defines the local offset from the parent's hotspot.
    *   `position.x`: 1.5
    *   `position.y`: 0

### `VerletPhysicsComponent`

This is the core component responsible for the tail's physics simulation.

*   **`num_points`**: The number of segments in the Verlet chain. A higher number results in a more detailed and flexible chain.
    *   Value: `10`
*   **`stiffness`**: Controls how rigid the chain segments are. Higher values make the chain less prone to stretching and bending.
    *   Value: `1.4`
*   **`velocity_dampening`**: Reduces the velocity of the points each frame, simulating air resistance or friction.
    *   Value: `0.9`
*   **`resting_distance`**: The ideal distance between adjacent points in the chain when no forces are applied.
    *   Value: `2`
*   **`simulate_wind`**: Enables or disables wind simulation for the tail.
    *   Value: `1` (Enabled)
*   **`wind_change_speed`**: How quickly the wind direction and strength can change.
    *   Value: `0.25`
*   **`simulate_gravity`**: Enables or disables gravity's effect on the tail.
    *   Value: `1` (Enabled)
*   **`collide_with_cells`**: Determines if the tail segments should collide with the game's cell-based environment.
    *   Value: `1` (Enabled)

### `Base` Components

These elements define the visual and physical parts that make up the Verlet chain. Each `Base` tag points to an XML file defining a segment of the tail. The repetition of certain files (`tail_verlet_2.xml`, `tail_verlet_3.xml`) indicates multiple instances of those specific segments, creating a varied tail structure.

*   `data/entities/verlet_chains/tail/tail_parts/tail_verlet_1.xml`
*   `data/entities/verlet_chains/tail/tail_parts/tail_verlet_2.xml`
*   `data/entities/verlet_chains/tail/tail_parts/tail_verlet_2.xml`
*   `data/entities/verlet_chains/tail/tail_parts/tail_verlet_3.xml`
*   `data/entities/verlet_chains/tail/tail_parts/tail_verlet_3.xml`
*   `data/entities/verlet_chains/tail/tail_parts/tail_verlet_3.xml`