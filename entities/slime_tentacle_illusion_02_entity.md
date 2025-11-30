---
title: Slime Tentacle Illusion 02 Entity
category: entities
---

# Slime Tentacle Illusion 02 Entity

This entity defines a segment of a slime tentacle, specifically an "illusion" variant, likely used for visual effects or less physically interactive parts of a tentacle. It inherits its core functionality from `slime_tentacle_piece.xml` and `slime_tentacle_piece_thin.xml`, with modifications to its sprite's alpha.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle segment, allowing it to behave like a chain of connected points.

| Attribute           | Value   | Description                                                              |
| :------------------ | :------ | :----------------------------------------------------------------------- |
| `stiffness`         | `1.25`  | Controls how rigid the connections between points are. Higher values mean less bending. |
| `num_points`        | `6`     | The number of points that make up this physics chain.                    |
| `velocity_dampening`| `0.8`   | Reduces the velocity of the points over time, simulating friction or air resistance. |
| `resting_distance`  | `2.0`   | The preferred distance between connected points when the chain is at rest. |

### Base Components (Inheritance)

This entity utilizes multiple `<Base>` tags to inherit properties from other entity files.

*   **`data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece.xml`**: This is inherited three times, suggesting it forms the bulk of the tentacle.
*   **`data/entities/verlet_chains/slime_tentacle/slime_tentacle_piece_thin.xml`**: This is inherited twice, likely for thinner sections of the tentacle.

### SpriteComponent (Applied via Inheritance)

Each inherited `<Base>` component includes a `<SpriteComponent>` with `alpha="0.5"`. This indicates that all parts of this tentacle illusion will have a semi-transparent appearance.