---
title: Summon Portal (Teleport)
category: entities
---

# Summon Portal (Teleport)

This entity defines a special type of portal that instantly teleports the player to a fixed location. It's designed to be used as a building or a spell effect.

## Key Components and Attributes

### `TeleportComponent`

This is the core component responsible for the teleportation functionality.

| Attribute                 | Description                                                                 | Value Example       |
| :------------------------ | :-------------------------------------------------------------------------- | :------------------ |
| `target_x_is_absolute_position` | If `1`, `target.x` is an absolute world coordinate. Otherwise, it's relative. | `1`                 |
| `target_y_is_absolute_position` | If `1`, `target.y` is an absolute world coordinate. Otherwise, it's relative. | `1`                 |
| `target.x`                | The X-coordinate of the teleport destination.                               | `-4830`             |
| `target.y`                | The Y-coordinate of the teleport destination.                               | `15009`             |

### `HitboxComponent`

Defines the collision area of the portal.

| Attribute   | Description                               | Value Example |
| :---------- | :---------------------------------------- | :------------ |
| `aabb_min_x` | Minimum X-coordinate of the bounding box. | `-15`         |
| `aabb_min_y` | Minimum Y-coordinate of the bounding box. | `-15`         |
| `aabb_max_x` | Maximum X-coordinate of the bounding box. | `15`          |
| `aabb_max_y` | Maximum Y-coordinate of the bounding box. | `15`          |

### `UIInfoComponent`

Provides information for the user interface, such as the name displayed.

| Attribute | Description                               | Value Example          |
| :-------- | :---------------------------------------- | :--------------------- |
| `name`    | The internal name or localization key.    | `$teleport_strange_stable` |

### `LightComponent`

Adds visual lighting effects to the portal. There are two instances, likely for different intensity or visual layers.

| Attribute     | Description                               | Value Example |
| :------------ | :---------------------------------------- | :------------ |
| `_enabled`    | Whether the light is active.              | `1`           |
| `radius`      | The radius of the light effect.           | `255` or `64` |
| `fade_out_time` | How long it takes for the light to fade.  | `1.5`         |
| `r`, `g`, `b` | RGB color values for the light.           | `64`, `100`, `255` |
| `offset_y`    | Vertical offset of the light source.      | `-16`         |

### `ParticleEmitterComponent`

These components generate visual particle effects around the portal.

| Attribute                 | Description                                                                 | Value Example       |
| :------------------------ | :-------------------------------------------------------------------------- | :------------------ |
| `emitted_material_name`   | The material name of the particles to emit.                                 | `spark_purple`      |
| `lifetime_min`, `lifetime_max` | The minimum and maximum duration of each particle.                          | `3` to `4`          |
| `count_min`, `count_max`  | The number of particles emitted per burst.                                  | `115` or `1`        |
| `area_circle_radius.min`, `area_circle_radius.max` | The radius of the area where particles are emitted.                         | `15` or `0`         |
| `cosmetic_force_create`   | If `1`, particles are purely cosmetic and don't interact physically.        | `1`                 |
| `velocity_always_away_from_center` | If `1`, particles are pushed away from the center.                        | `11` or `0`         |
| `render_back`             | If `1`, particles are rendered behind other elements.                       | `1`                 |
| `is_emitting`             | If `1`, the emitter is active.                                              | `1`                 |

### `SpriteComponent`

Defines the visual appearance of the portal.

| Attribute   | Description                               | Value Example                        |
| :---------- | :---------------------------------------- | :----------------------------------- |
| `image_file` | Path to the sprite image file.            | `data/buildings_gfx/teleport_center.xml` |
| `z_index`   | Rendering order. Higher values are on top. | `1`                                  |
| `additive`  | If `1`, uses additive blending for rendering. | `1`                                  |

### `AudioLoopComponent`

Plays looping sound effects associated with the portal.

| Attribute     | Description                               | Value Example             |
| :------------ | :---------------------------------------- | :------------------------ |
| `file`        | Path to the audio file.                   | `data/audio/Desktop/misc.snd` |
| `event_name`  | The specific sound event to play.         | `misc/teleport_loop` or `misc/teleport_emitter_loop` |
| `auto_play`   | If `1`, the sound starts automatically.   | `1`                       |

### `LuaComponent`

Attaches a Lua script to the entity, allowing for custom logic.

| Attribute               | Description                                                                 | Value Example                                       |
| :---------------------- | :-------------------------------------------------------------------------- | :-------------------------------------------------- |
| `script_portal_teleport_used` | The path to the Lua script executed when the portal is used.                | `data/scripts/buildings/teleport_summon_portal_used.lua` |

## Modding Considerations

*   **Teleport Destination:** The `target.x` and `target.y` attributes in `TeleportComponent` are crucial for defining where the portal sends the player. Modifying these will change the destination.
*   **Visuals:** Adjusting `LightComponent` and `ParticleEmitterComponent` attributes can alter the portal's appearance and particle effects.
*   **Sound:** The `AudioLoopComponent` can be modified to change the sounds associated with the portal.
*   **Scripted Behavior:** The `LuaComponent` points to a script that likely handles post-teleport logic, such as disabling the portal to prevent loops. This script can be modified for custom behaviors.