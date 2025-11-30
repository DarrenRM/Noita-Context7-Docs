---
title: Mystery Teleport Entity
category: entities
---

# Mystery Teleport Entity

This document describes the configuration for the "Mystery Teleport" entity in Noita, focusing on its functional and visual components relevant for AI-assisted modding.

## Core Functionality

### TeleportComponent

This component dictates the teleportation behavior of the entity.

| Attribute                  | Description                                                                 |
| :------------------------- | :-------------------------------------------------------------------------- |
| `target_x_is_absolute_position` | If `1`, `target.x` is an absolute world coordinate. Otherwise, it's relative. |
| `target_y_is_absolute_position` | If `1`, `target.y` is an absolute world coordinate. Otherwise, it's relative. |
| `target.x`                 | The X-coordinate of the teleport destination.                               |
| `target.y`                 | The Y-coordinate of the teleport destination.                               |

## Visual and Audio Components

### HitboxComponent

Defines the collision area of the teleport entity.

| Attribute    | Description                               |
| :----------- | :---------------------------------------- |
| `aabb_min_x` | Minimum X-axis bounding box coordinate.   |
| `aabb_min_y` | Minimum Y-axis bounding box coordinate.   |
| `aabb_max_x` | Maximum X-axis bounding box coordinate.   |
| `aabb_max_y` | Maximum Y-axis bounding box coordinate.   |

### UIInfoComponent

Provides information for UI elements, such as the entity's name.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `name`    | The internal name or localization key.    |

### LightComponent (x2)

These components add lighting effects to the entity, contributing to its visual presence.

| Attribute     | Description