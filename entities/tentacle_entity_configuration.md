---
title: Tentacle Entity Configuration
category: entities
---

# Tentacle Entity Configuration

This document details the configuration for a generic "tentacle" entity in Noita, focusing on its physics and inheritance.

## Core Components

### VerletPhysicsComponent

This component defines the physics simulation for the tentacle, likely controlling its segmented movement and flexibility.

| Attribute             | Value   | Description                                                                 |
| :-------------------- | :------ | :-------------------------------------------------------------------------- |
| `num_points`          | `15`    | The number of points used in the Verlet simulation, affecting its smoothness. |
| `stiffness`           | `1.0`   | Controls how rigid the tentacle segments are. Higher values mean less bend. |
| `velocity_dampening`  | `0.9`   | Reduces the velocity of points over time, simulating friction or air resistance. |
| `resting_distance`    | `4`     | The preferred distance between connected points when not under tension.     |
| `simulate_gravity`    | `1`     | Enables gravity simulation for the tentacle points.                         |
| `constrain_stretching`| `1`     | Prevents the tentacle segments from stretching beyond their resting distance. |

### InheritTransformComponent

This component is present but empty, suggesting it might be a placeholder or that its functionality is inherited from a base entity.

## Inheritance

The tentacle entity is constructed by inheriting from multiple base entity configurations. This allows for modularity and reuse of tentacle segment designs.

| Base File Path                                         | Description