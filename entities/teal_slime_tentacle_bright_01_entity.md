---
title: Teal Slime Tentacle Bright 01 Entity
category: entities
---

---

# Teal Slime Tentacle Bright 01 Entity

This document describes the `tealslime_tentacle_bright_01.xml` entity, which defines a segment of a teal slime tentacle. It utilizes Verlet physics to simulate a chain-like structure.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle.

| Attribute           | Value   | Description                                                                 |
| :------------------ | :------ | :-------------------------------------------------------------------------- |
| `stiffness`         | `1.25`  | Controls how rigid the tentacle segments are. Higher values mean less bend. |
| `num_points`        | `5`     | The number of points (segments) that make up this tentacle piece.           |
| `velocity_dampening`| `0.8`   | Reduces the velocity of the tentacle segments over time, causing it to settle. |
| `resting_distance`  | `1.0`   | The ideal distance between adjacent points in the chain when at rest.       |

### Base Components

This entity inherits its visual and functional properties from other base entities, creating the tentacle's appearance and behavior.

*   `data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece_bright.xml` (Inherited 3 times)
*   `data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece_thin.xml` (Inherited 1 time)

These base files likely define the sprite, collision, and other specific behaviors for different parts of the tentacle.

## Summary

The `tealslime_tentacle_bright_01.xml` entity is a foundational piece for creating teal slime tentacles in Noita. Its `VerletPhysicsComponent` is crucial for its flexible, chain-like movement, with parameters like `stiffness` and `num_points` directly influencing its physical properties. The entity's appearance and specific behaviors are derived from inherited base entities, allowing for modular design.