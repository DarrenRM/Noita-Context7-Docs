---
title: Shorter Verlet Vine
category: entities
---

# Shorter Verlet Vine

This entity defines a shorter, segmented vine using the Verlet physics system. It's composed of multiple vine segments linked together.

## VerletPhysicsComponent

This component governs the physics simulation for the vine.

| Attribute           | Value   | Description                                                                 |
| :------------------ | :------ | :-------------------------------------------------------------------------- |
| `num_points`        | `4`     | The number of points (segments) in the Verlet chain.                        |
| `stiffness`         | `1.0`   | Controls how rigid the vine segments are. Higher values mean less bending. |
| `velocity_dampening`| `0.9`   | Reduces the velocity of the vine segments over time, making it settle.      |
| `resting_distance`  | `4`     | The ideal distance between connected points (segments).                     |
| `simulate_wind`     | `1`     | Enables wind simulation for the vine.                                       |
| `wind_change_speed` | `0.25`  | How quickly the wind's direction and strength can change.                   |
| `simulate_gravity`  | `1`     | Enables gravity simulation for the vine.                                    |

## Base Components

The vine is constructed from several pre-defined vine segment entities.

*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_8.xml`

## AudioComponent

This component handles audio events related to the vine.

| Attribute   | Value                         | Description                               |
| :---------- | :---------------------------- | :---------------------------------------- |
| `file`      | `data/audio/Desktop/materials.bank` | The audio bank containing vine sounds.    |
| `event_root`| `collision/vine`              | The root event name for vine collisions.  |