---
title: Verlet Cape Test Entity
category: entities
---

# Verlet Cape Test Entity

This entity demonstrates the use of the `VerletPhysicsComponent` to create a cloth-like effect, specifically for testing a cape. It's designed to be interactive with the mouse for debugging purposes.

## Entity Components

### VerletPhysicsComponent

This component governs the cloth simulation properties.

| Attribute             | Value   | Description                                                                 |
| :-------------------- | :------ | :-------------------------------------------------------------------------- |
| `num_points`          | `100`   | The number of points used to simulate the cloth. Higher values mean more detail. |
| `width`               | `10`    | The width of the cloth simulation.                                          |
| `type`                | `CLOTH` | Specifies the type of simulation, in this case, cloth.                      |
| `stiffness`           | `1.5`   | Controls how rigid the cloth is. Higher values make it stiffer.             |
| `velocity_dampening`  | `0.7`   | Reduces the velocity of the cloth over time, making it settle down.         |
| `simulate_wind`       | `1`     | Enables wind simulation affecting the cloth.                                |
| `resting_distance`    | `1.5`   | The preferred distance between points when the cloth is at rest.            |
| `constrain_stretching`| `1`     | Prevents the cloth from stretching beyond its natural length.               |
| `collide_with_cells`  | `1`     | Enables collision detection with the environment's cells.                   |
| `mass_min`            | `0.1`   | The minimum mass of individual cloth points.                                |
| `mass_max`            | `0.2`   | The maximum mass of individual cloth points.                                |
| `pixelate_sprite_transforms` | `0` | Disables pixelation of sprite transformations during simulation.            |

### DebugFollowMouseComponent

This component is for debugging and allows the entity to follow the mouse cursor. This is not intended for gameplay and would typically be removed in a final mod.