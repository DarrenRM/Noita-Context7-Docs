---
title: Beginning Portal Entity
category: entities
---

# Beginning Portal Entity

This entity represents a special type of portal that teleports the player to a fixed location. It's often used for starting points or specific transitions within the game.

## Key Components

### TeleportComponent
This component defines the destination of the teleport.

| Attribute                  | Description                                                                 |
| :------------------------- | :-------------------------------------------------------------------------- |
| `target_x_is_absolute_position` | If `1`, `target.x` is an absolute world coordinate. Otherwise, it's relative. |
| `target_y_is_absolute_position` | If `1`, `target.y` is an absolute world coordinate. Otherwise, it's relative. |
| `target.x`                 | The X-coordinate of the teleport destination.                               |
| `target.y`                 | The Y-coordinate of the teleport destination.                               |

### HitboxComponent
Defines the collision area of the portal.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `aabb_min_x` | Minimum X-coordinate of the bounding box. |
| `aabb_min_y` | Minimum Y-coordinate of the bounding box. |
| `aabb_max_x` | Maximum X-coordinate of the bounding box. |
| `aabb_max_y` | Maximum Y-coordinate of the bounding box. |

### UIInfoComponent
Provides information for UI elements, such as the portal's name.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `name`    | The internal name or localization key.    |

### LightComponent
Adds visual lighting effects to the portal. This entity has two `LightComponent` instances for different colored glows.

| Attribute       | Description                                                                 |
| :-------------- | :-------------------------------------------------------------------------- |
| `radius`        | The radius of the light effect.                                             |
| `fade_out_time` | How long it takes for the light to fade out.                                |
| `r`, `g`, `b`   | RGB color values for the light.                                             |
| `offset_y`      | Vertical offset for the light source.                                       |

### ParticleEmitterComponent
Responsible for generating visual particle effects around the portal. This entity has two `ParticleEmitterComponent` instances, likely for different visual styles or densities of particles.

| Attribute                     | Description