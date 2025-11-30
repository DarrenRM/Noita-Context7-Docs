---
title: Teleport Lake Entity
category: entities
---

---

# Teleport Lake Entity

This document describes the `teleport_lake.xml` entity, which represents a teleportation point in Noita.

## Core Functionality

The primary function of this entity is to teleport the player to a predefined location.

### `TeleportComponent`

This component defines the teleportation behavior.

| Attribute                     | Description                                                                 |
| :---------------------------- | :-------------------------------------------------------------------------- |
| `target_x_is_absolute_position` | If `1`, `target.x` is an absolute world coordinate.                         |
| `target_y_is_absolute_position` | If `1`, `target.y` is an absolute world coordinate.                         |
| `target.x`                    | The X-coordinate of the teleportation destination.                          |
| `target.y`                    | The Y-coordinate of the teleportation destination.                          |

## Visual and Audio Components

This entity utilizes several components to create visual effects and sound.

### `UIInfoComponent`

Provides basic information for UI elements.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `name`    | The internal name of the entity (`$teleport_world`). |

### `HitboxComponent`

Defines the collision area of the entity.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `aabb_min_x` | Minimum X-coordinate of the bounding box. |
| `aabb_min_y` | Minimum Y-coordinate of the bounding box. |
| `aabb_max_x` | Maximum X-coordinate of the bounding box. |
| `aabb_max_y` | Maximum Y-coordinate of the bounding box. |

### `LightComponent`

Adds a light source to the entity. There are two instances, likely for different light effects or layers.

| Attribute     | Description