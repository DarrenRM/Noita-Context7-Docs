---
title: Teleport Teleroom 1
category: entities
---

# Teleport Teleroom 1

This entity defines a functional teleportation pad, likely used for transitioning between areas in Noita. It's activated by liquid and visually represented by particle effects and lighting.

## Key Components

### TeleportComponent

This is the core component responsible for the teleportation functionality.

| Attribute   | Value      | Description                                                                 |
| :---------- | :--------- | :-------------------------------------------------------------------------- |
| `target.x`  | `-12800`   | The X-coordinate of the teleportation destination.                          |
| `target.y`  | `7008`     | The Y-coordinate of the teleportation destination.                          |
| `_tags`     | `enabled_by_liquid` | This tag indicates the teleport is activated when submerged in liquid. |

### HitboxComponent

Defines the physical boundaries of the teleport pad.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_min_x`| `-15` | Minimum X-axis bounding box coordinate.   |
| `aabb_min_y`| `-15` | Minimum Y-axis bounding box coordinate.   |
| `aabb_max_x`| `15`  | Maximum X-axis bounding box coordinate.   |
| `aabb_max_y`| `15`  | Maximum Y-axis bounding box coordinate.   |
| `_tags`     | `enabled_by_liquid` | Inherits activation condition. |

### LightComponent

Adds visual illumination to the teleport pad. There are two `LightComponent` instances, likely for different visual effects or intensities.

| Attribute       | Value   | Description                                                              |
| :-------------- | :------ | :----------------------------------------------------------------------- |
| `_tags`         | `enabled_by_liquid` | Light is active when submerged in liquid.                                |
| `_enabled`      | `1`     | The light component is enabled by default.                               |
| `radius`        | `255`   | The radius of the light's influence.                                     |
| `fade_out_time` | `1.5`   | The time it takes for the light to fade out.                             |
| `r`, `g`, `b`   | `64`, `100`, `255` | RGB color values for the light (a bluish hue).                           |
| `offset_y`      | `-16`   | Vertical offset for the light's position.                                |

### SpriteParticleEmitterComponent

Responsible for emitting visual particle effects that swirl around the teleport pad.

| Attribute                 | Value      | Description