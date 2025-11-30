---
title: Teleport Hourglass Entity
category: entities
---

# Teleport Hourglass Entity

This document details the `teleport_hourglass.xml` entity, which functions as a teleportation device in Noita.

## Core Functionality

The primary purpose of this entity is to teleport the player to a predefined location when specific conditions are met.

### `TeleportComponent`

This component handles the teleportation logic.

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `target_x_is_absolute_position` | If `1`, `target.x` is an absolute world coordinate.                       |
| `target_y_is_absolute_position` | If `1`, `target.y` is an absolute world coordinate.                       |
| `target.x`             | The X-coordinate of the teleportation destination.                          |
| `target.y`             | The Y-coordinate of the teleportation destination.                          |

## Visual and Audio Elements

These components define the visual and auditory feedback associated with the hourglass.

### `HitboxComponent`

Defines the collision area for the entity.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `aabb_min_x` | Minimum X-axis bounding box coordinate.   |
| `aabb_min_y` | Minimum Y-axis bounding box coordinate.   |
| `aabb_max_x` | Maximum X-axis bounding box coordinate.   |
| `aabb_max_y` | Maximum Y-axis bounding box coordinate.   |

### `UIInfoComponent`

Provides information displayed in the UI.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `name`    | The in-game name of the entity.           |

### `LightComponent`

Adds a light source to the entity. Multiple instances can create layered lighting effects.

| Attribute      | Description                                                              |
| :------------- | :----------------------------------------------------------------------- |
| `radius`       | The radius of the light.                                                 |
| `fade_out_time`| How long it takes for the light to fade out.                             |
| `r`, `g`, `b`  | Red, Green, and Blue color values for the light.                         |
| `offset_y`     | Vertical offset for the light's position.                                |

### `ParticleEmitterComponent`

Responsible for generating visual particle effects.

| Attribute                     | Description