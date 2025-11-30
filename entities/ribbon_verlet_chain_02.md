---
title: Ribbon Verlet Chain 02
category: entities
---

# Ribbon Verlet Chain 02

This document describes the `ribbon_02.xml` entity, which defines a specific type of Verlet chain used for creating ribbon-like physics objects in Noita.

## Entity Definition

The core of this entity is the `VerletPhysicsComponent`, which dictates how the chain behaves. It inherits its visual and structural components from a base file.

### Key Components

*   **`VerletPhysicsComponent`**: This is the primary component responsible for the physics simulation of the ribbon.

    *   **`stiffness`**: `1.9` - Controls how rigid the chain segments are. Higher values mean less bending.
    *   **`num_points`**: `10` - Defines the number of individual points (nodes) that make up the Verlet chain. More points result in a smoother, more detailed chain.
    *   **`velocity_dampening`**: `0.85` - Reduces the velocity of the points over time, causing the chain to eventually settle.
    *   **`resting_distance`**: `3.5` - The ideal distance between adjacent points when the chain is not under stress.
    *   **`simulate_gravity`**: `1` - Enables gravity to affect the chain points.
    *   **`wind_change_speed`**: `1.323` - Influences how quickly the simulated wind affects the chain's movement.
    *   **`mass_min`**: `0.13` - The minimum mass assigned to individual points in the chain.
    *   **`mass_max`**: `0.16` - The maximum mass assigned to individual points in the chain.

*   **`Base`**: The entity reuses the `verlet_1.xml` file multiple times. This suggests that `verlet_1.xml` likely defines the individual segments or nodes of the ribbon, and this entity is instantiating ten of them to form the chain.

## Usage

This entity is likely used in Noita to create dynamic, flowing ribbon-like visual elements that react to physics, wind, and other environmental factors. The multiple `Base` inclusions of `verlet_1.xml` indicate a chain of 10 segments.