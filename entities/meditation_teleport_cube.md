---
title: Meditation Teleport Cube
category: entities
---

# Meditation Teleport Cube

This entity defines a teleportation cube that activates after a period of meditation. It utilizes various components to handle its teleportation logic, visual effects, and audio cues.

## Core Functionality

### TeleportComponent

This component handles the core teleportation behavior.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `_tags`                   | `enabled_by_meditation`: Indicates this component is active when meditation is enabled. |
| `_enabled`                | `0`: Initially disabled, activated by game logic.                           |
| `target_x_is_absolute_position` | `1`: The `target.x` value is an absolute world coordinate.                  |
| `target_y_is_absolute_position` | `1`: The `target.y` value is an absolute world coordinate.                  |
| `target.x`                | `-4345`: The absolute X-coordinate to teleport to.                          |
| `target.y`                | `2365`: The absolute Y-coordinate to teleport to.                           |

### HitboxComponent

Defines the collision area for the teleport cube.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `_tags`   | `enabled_by_meditation`: Active when meditation is enabled. |
| `_enabled`| `0`: Initially disabled.                  |
| `aabb_min_x` | `-15`: Minimum X-axis bounding box coordinate. |
| `aabb_min_y` | `-15`: Minimum Y-axis bounding box coordinate. |
| `aabb_max_x` | `15`: Maximum X-axis bounding box coordinate.  |
| `aabb_max_y` | `15`: Maximum Y-axis bounding box coordinate.  |

## Visual and Audio Effects

### UIInfoComponent

Provides information for UI elements, such as the entity's name.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `_tags`   | `enabled_by_meditation`: Active when meditation is enabled. |
| `_enabled`| `0`: Initially disabled.                  |
| `name`    | `$teleport_generic`: The internal name for UI display. |

### LightComponent (x2)

These components add lighting effects to the teleport cube.

| Attribute      | Description                                                              |
| :------------- | :----------------------------------------------------------------------- |
| `_tags`        | `enabled_by_meditation`: Active when meditation is enabled.              |
| `_enabled`     | `0`: Initially disabled.                                                 |
| `radius`       | `255` / `64`: The radius of the light effect.                            |
| `fade_out_time`| `1.5`: Duration for the light to fade out.                               |
| `r`, `g`, `b`  | `64`, `100`, `255`: RGB color values for the light (a shade of blue).    |
| `offset_y`     | `-16`: Vertical offset for the light source.                             |

### ParticleEmitterComponent (x3)

These components generate various particle effects for visual flair.

| Attribute                 | Description