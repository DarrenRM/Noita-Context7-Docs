---
title: Teleport Teleroom Entity
category: entities
---

# Teleport Teleroom Entity

This document describes the `teleport_teleroom.xml` entity, which represents a teleportation pad in Noita. It's primarily used for instant travel between specific points in the game world.

## Key Components

This entity utilizes several components to define its behavior and appearance. The most important ones are:

### TeleportComponent

This component handles the core teleportation logic.

| Attribute                     | Description                                                                 |
| :---------------------------- | :-------------------------------------------------------------------------- |
| `target_x_is_absolute_position` | If `1`, `target.x` is an absolute world coordinate.                         |
| `target_y_is_absolute_position` | If `1`, `target.y` is an absolute world coordinate.                         |
| `target.x`                    | The X-coordinate of the teleportation destination.                          |
| `target.y`                    | The Y-coordinate of the teleportation destination.                          |

### HitboxComponent

Defines the physical boundaries of the teleport pad.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `aabb_min_x`  | Minimum X-axis bounding box coordinate.   |
| `aabb_min_y`  | Minimum Y-axis bounding box coordinate.   |
| `aabb_max_x`  | Maximum X-axis bounding box coordinate.   |
| `aabb_max_y`  | Maximum Y-axis bounding box coordinate.   |

### LightComponent

Adds visual lighting effects to the entity. There are two instances, likely for different visual layers or intensities.

| Attribute       | Description                                     |
| :-------------- | :---------------------------------------------- |
| `_enabled`      | Whether the light component is active (`1` or `0`). |
| `radius`        | The radius of the light effect.                 |
| `fade_out_time` | How long it takes for the light to fade out.    |
| `r`, `g`, `b`   | RGB color values for the light.                 |
| `offset_y`      | Vertical offset for the light's position.       |

### SpriteParticleEmitterComponent

Responsible for emitting visual particles that contribute to the teleportation effect.

| Attribute                 | Description