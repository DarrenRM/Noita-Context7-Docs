---
title: Teleport Robot Egg Return
category: data/entities
---

# Teleport Robot Egg Return

This entity represents a special teleportation point designed to return robot eggs. It defines the destination, visual effects, and audio cues associated with its activation.

## Key Components

### TeleportComponent
This component dictates the teleportation behavior.

| Attribute                  | Value   | Description                                                                 |
| :------------------------- | :------ | :-------------------------------------------------------------------------- |
| `target_x_is_absolute_position` | `1`     | Indicates that `target.x` is an absolute world coordinate.                  |
| `target_y_is_absolute_position` | `1`     | Indicates that `target.y` is an absolute world coordinate.                  |
| `target.x`                 | `190`   | The absolute X-coordinate of the teleportation destination.                 |
| `target.y`                 | `6650`  | The absolute Y-coordinate of the teleportation destination.                 |

### HitboxComponent
Defines the physical boundaries of the entity.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_min_x` | `-15` | Minimum X-axis bounding box coordinate.   |
| `aabb_min_y` | `-15` | Minimum Y-axis bounding box coordinate.   |
| `aabb_max_x` | `15`  | Maximum X-axis bounding box coordinate.   |
| `aabb_max_y` | `15`  | Maximum Y-axis bounding box coordinate.   |

### UIInfoComponent
Provides information for UI elements, such as the entity's name.

| Attribute | Value                   | Description                               |
| :-------- | :---------------------- | :---------------------------------------- |
| `name`    | `$teleport_strange_stable` | The internal name for UI display.         |

### LightComponent
Adds a light source to the entity for visual effect.

| Attribute     | Value   | Description                                                              |
| :------------ | :------ | :----------------------------------------------------------------------- |
| `_enabled`    | `1`     | Enables the light component.                                             |
| `radius`      | `255`   | The radius of the light.                                                 |
| `fade_out_time` | `1.5`   | The time it takes for the light to fade out.                             |
| `r`           | `64`    | Red component of the light color.                                        |
| `g`           | `100`   | Green component of the light color.                                      |
| `b`           | `255`   | Blue component of the light color.                                       |
| `offset_y`    | `-16`   | Vertical offset of the light source.                                     |

*Note: There are two `LightComponent` instances, likely for different visual effects or layering.*

### ParticleEmitterComponent
Responsible for generating visual particle effects.

| Attribute                  | Value   | Description