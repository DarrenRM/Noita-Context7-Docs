---
title: Dark Shorter Verlet Vine
category: entities
---

# Dark Shorter Verlet Vine

This entity defines a shorter, darker variant of a verlet vine. It utilizes the `VerletPhysicsComponent` to simulate its chain-like behavior and `MoveToSurfaceOnCreateComponent` to attach itself to surfaces.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the vine.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `num_points`          | The number of points in the verlet chain (6).                               |
| `stiffness`           | Controls how rigid the vine is (1.0). Higher values mean less bending.     |
| `velocity_dampening`  | Reduces the velocity of the verlet points each frame (0.9).                 |
| `resting_distance`    | The ideal distance between adjacent points in the chain (4).                |
| `pixelate_sprite_transforms` | Enables pixelation effects on sprite transformations (1).                  |
| `follow_entity_transform` | Determines if the vine follows the transform of another entity (0).       |
| `simulate_wind`       | Enables wind simulation for the vine (1).                                   |
| `wind_change_speed`   | Controls how quickly wind direction and strength change (0.25).             |
| `simulate_gravity`    | Enables gravity simulation for the vine (1).                                |

### Base Components

These components define the visual parts of the vine. Each `Base` tag points to a separate XML file that defines a segment of the vine.

*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_8.xml`

### MoveToSurfaceOnCreateComponent

This component ensures the vine attaches itself to a surface when created.

| Attribute                | Description                                                                 |
| :----------------------- | :-------------------------------------------------------------------------- |
| `lookup_radius`          | The radius to search for a surface to attach to (20).                       |
| `verlet_min_joint_distance` | The minimum distance between verlet joints when attaching (10).             |
| `type`                   | The type of attachment, `VERLET_ROPE_ONE_JOINT` indicates a single attachment point. |

### AudioComponent

This component handles the audio events associated with the vine.

| Attribute   | Description                                                                 |
| :---------- | :-------------------------------------------------------------------------- |
| `file`      | The audio bank file containing the sound events (`data/audio/Desktop/materials.bank`). |
| `event_root` | The root event name for vine-related sounds (`collision/vine`).             |