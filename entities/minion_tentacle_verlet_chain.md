---
title: Minion Tentacle (Verlet Chain)
category: entities
---

# Minion Tentacle (Verlet Chain)

This entity defines a minion tentacle that utilizes a Verlet physics chain for its movement and behavior. It inherits its core functionality from several base entity files, creating a segmented, flexible appendage.

## Key Components

### VerletPhysicsComponent

This component is crucial for defining the physics of the tentacle's chain.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `num_points`          | The number of segments in the Verlet chain (10 in this case).               |
| `stiffness`           | Controls how rigid the chain segments are (1.0 indicates moderate stiffness). |
| `velocity_dampening`  | Reduces the velocity of the chain segments over time (0.9 means significant dampening). |
| `resting_distance`    | The preferred distance between adjacent points in the chain (4 units).      |
| `simulate_gravity`    | Whether gravity affects the chain segments (1 means gravity is simulated).  |
| `constrain_stretching`| Prevents the chain from stretching beyond its resting distance (1 means enabled). |

### Base Components

The tentacle's appearance and specific behaviors are built upon several inherited entity files. These files likely define the visual representation of each tentacle segment and potentially unique interactions or animations.

*   `data/entities/animals/special/verlet_chains/minion_tentacle_verlet_1.xml`
*   `data/entities/animals/special/verlet_chains/minion_tentacle_verlet_2.xml` (repeated multiple times)
*   `data/entities/animals/special/verlet_chains/minion_tentacle_verlet_3.xml` (repeated multiple times)
*   `data/entities/animals/special/verlet_chains/minion_tentacle_verlet_4.xml`

These `Base` tags indicate that the primary structure and visual elements of the tentacle are defined in these separate files, allowing for modularity and reuse. The repetition of certain files suggests variations or specific roles for those segments within the overall tentacle structure.