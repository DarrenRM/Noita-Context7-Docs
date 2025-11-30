---
title: Verlet Vine Short Pixel Scene
category: entities
---

# Verlet Vine Short Pixel Scene

This entity defines a short, pixelated vine segment using the Verlet physics system. It's designed to simulate natural swaying and interaction with wind.

## VerletPhysicsComponent

This component governs the physics simulation of the vine.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `num_points`          | The number of points used to simulate the vine's chain.                     |
| `stiffness`           | Controls how rigid the vine is. Higher values mean less bending.            |
| `velocity_dampening`  | Reduces the velocity of the vine points over time, simulating friction.     |
| `resting_distance`    | The ideal distance between adjacent points when the vine is not stretched.  |
| `pixelate_sprite_transforms` | Enables pixelation effects on the sprite as it deforms.                 |
| `follow_entity_transform` | If set to 1, the vine will follow the transform of its parent entity.     |
| `simulate_wind`       | Enables simulation of wind forces acting on the vine.                       |
| `wind_change_speed`   | Controls how quickly wind direction and strength can change.                |
| `simulate_gravity`    | Enables simulation of gravity acting on the vine.                           |

## Base Components

This entity is composed of several smaller vine segments, defined by their respective XML files. These files likely contain the visual sprites and collision data for each part of the vine.

*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_5.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_8.xml`

## AudioComponent

This component handles audio events related to the vine.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `file`      | The audio bank file containing the sound events. |
| `event_root`| The root event name for vine-related sounds.    |