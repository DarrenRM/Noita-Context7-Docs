---
title: Teleport End Wall
category: entities
---

# Teleport End Wall

This entity represents the destination point for teleportation in Noita. When a player or entity enters a teleportation trigger, they are moved to the location defined by this entity.

## Key Components

### TeleportComponent

This component defines the destination of the teleportation.

| Attribute                  | Description                                                                 |
| :------------------------- | :-------------------------------------------------------------------------- |
| `target_x_is_absolute_position` | If `1`, `target.x` is an absolute world coordinate. Otherwise, it's relative. |
| `target_y_is_absolute_position` | If `1`, `target.y` is an absolute world coordinate. Otherwise, it's relative. |
| `target.x`                 | The X-coordinate of the teleportation target.                               |
| `target.y`                 | The Y-coordinate of the teleportation target.                               |

### HitboxComponent

Defines the collision area of the teleport end wall.

| Attribute    | Description                               |
| :----------- | :---------------------------------------- |
| `aabb_min_x` | Minimum X-coordinate of the bounding box. |
| `aabb_min_y` | Minimum Y-coordinate of the bounding box. |
| `aabb_max_x` | Maximum X-coordinate of the bounding box. |
| `aabb_max_y` | Maximum Y-coordinate of the bounding box. |

### UIInfoComponent

Provides information for the game's UI, such as the entity's name.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `name`    | The internal name of the entity.          |

### LightComponent

Adds a light source to the entity, contributing to the visual atmosphere.

| Attribute      | Description                                                              |
| :------------- | :----------------------------------------------------------------------- |
| `_enabled`     | Whether the light component is active (`1` for enabled, `0` for disabled). |
| `radius`       | The radius of the light's illumination.                                  |
| `fade_out_time`| The time it takes for the light to fade out.                             |
| `r`, `g`, `b`  | The RGB color values of the light.                                       |
| `offset_y`     | Vertical offset of the light source.                                     |

### SpriteParticleEmitterComponent

Responsible for generating visual particle effects around the teleport end wall.

| Attribute                 | Description