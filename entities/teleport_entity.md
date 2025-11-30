---
title: Teleport Entity
category: entities
---

# Teleport Entity

This document describes the `teleport.xml` entity, which functions as a teleportation point in Noita.

## Core Functionality

### `TeleportComponent`

This component defines the teleportation behavior.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `target_x_is_absolute_position` | If `1`, `target.x` and `target.y` are absolute world coordinates. Otherwise, they are relative to the current position. |
| `target.x`                | The X-coordinate of the teleportation destination.                          |
| `target.y`                | The Y-coordinate of the teleportation destination.                          |

## Visual and Audio Elements

### `HitboxComponent`

Defines the collision area for the teleport.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `aabb_min_x`  | Minimum X-axis bounding box coordinate.   |
| `aabb_min_y`  | Minimum Y-axis bounding box coordinate.   |
| `aabb_max_x`  | Maximum X-axis bounding box coordinate.   |
| `aabb_max_y`  | Maximum Y-axis bounding box coordinate.   |

### `UIInfoComponent`

Provides information for UI elements, such as the name displayed to the player.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `name`    | The internal name or localization key for the entity. |

### `LightComponent`

Adds lighting effects to the teleport. Multiple `LightComponent` instances can create layered lighting.

| Attribute       | Description                                                                 |
| :-------------- | :-------------------------------------------------------------------------- |
| `_enabled`      | Whether the light is active (`1` or `0`).                                   |
| `radius`        | The radius of the light effect.                                             |
| `fade_out_time` | How long it takes for the light to fade out.                                |
| `r`, `g`, `b`   | Red, Green, and Blue color values for the light (0-255).                  |
| `offset_y`      | Vertical offset for the light's position.                                   |

### `ParticleEmitterComponent`

Generates visual particle effects. This entity uses two emitters for distinct effects.

**Emitter 1 (Main Effect):**

| Attribute                   | Description