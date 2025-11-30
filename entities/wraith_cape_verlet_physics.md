---
title: Wraith Cape Verlet Physics
category: entities
---

# Wraith Cape Verlet Physics

This entity defines the core Verlet physics simulation for the Wraith Cape. It dictates how the cape segments behave and interact with each other and the environment.

## Key Components

### VerletPhysicsComponent

This component is responsible for the physics simulation of the cape.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `stiffness`           | Controls how rigid the cape segments are. Higher values mean less bending.   |
| `num_points`          | The number of simulated points that make up the cape.                       |
| `velocity_dampening`  | Reduces the velocity of the cape segments over time, simulating air resistance. |
| `resting_distance`    | The preferred distance between connected points when not under tension.     |
| `simulate_gravity`    | Whether gravity affects the cape segments.                                  |
| `mass_min`            | The minimum mass assigned to individual cape segments.                      |
| `mass_max`            | The maximum mass assigned to individual cape segments.                      |

### Base Components

These `<Base>` tags inherit and apply specific visual and physical properties to individual segments of the cape.

*   `data/entities/verlet_chains/wraith_cape/wraith_storm/parts/cape_verlet_1.xml`
*   `data/entities/verlet_chains/wraith_cape/wraith_storm/parts/cape_verlet_2.xml`
*   `data/entities/verlet_chains/wraith_cape/wraith_storm/parts/cape_verlet_3.xml`
*   `data/entities/verlet_chains/wraith_cape/wraith_storm/parts/cape_verlet_4.xml`