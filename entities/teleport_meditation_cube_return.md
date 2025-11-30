---
title: Teleport Meditation Cube Return
category: entities
---

# Teleport Meditation Cube Return

This entity represents a teleportation point that returns the player to a specific location. It's designed to be activated by liquids and features visual and audio effects.

## Key Components

### TeleportComponent

This component handles the teleportation logic.

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `_tags="enabled_by_liquid"` | The entity is activated when in contact with a liquid.                      |
| `target_x_is_absolute_position` | `1` indicates the `target.x` is an absolute world coordinate.             |
| `target_y_is_absolute_position` | `1` indicates the `target.y` is an absolute world coordinate.             |
| `target.x`             | The absolute X-coordinate to teleport to.                                   |
| `target.y`             | The absolute Y-coordinate to teleport to.                                   |

### HitboxComponent

Defines the collision area of the entity.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `_tags="enabled_by_liquid"` | The entity is activated when in contact with a liquid. |
| `aabb_min_x`  | Minimum X-axis bounding box coordinate.   |
| `aabb_min_y`  | Minimum Y-axis bounding box coordinate.   |
| `aabb_max_x`  | Maximum X-axis bounding box coordinate.   |
| `aabb_max_y`  | Maximum Y-axis bounding box coordinate.   |

### UIInfoComponent

Provides information for the user interface.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `_tags="enabled_by_liquid"` | The entity is activated when in contact with a liquid. |
| `name`    | The name displayed in the UI (`$teleport_back`). |

### LightComponent

Adds a light source to the entity. There are two instances, likely for different visual effects or intensities.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `_tags="enabled_by_liquid"` | The entity is activated when in contact with a liquid. |
| `_enabled="1"` | The light component is active.            |
| `radius`      | The radius of the light.                  |
| `fade_out_time` | How long it takes for the light to fade out. |
| `r`, `g`, `b` | RGB color values for the light.           |
| `offset_y`    | Vertical offset of the light.             |

### ParticleEmitterComponent

Responsible for emitting visual particles. There are two instances with slightly different configurations.

| Attribute                     | Description