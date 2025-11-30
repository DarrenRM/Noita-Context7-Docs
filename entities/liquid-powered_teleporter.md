---
title: Liquid-Powered Teleporter
category: entities
---

# Liquid-Powered Teleporter

This entity defines a teleporter that is activated by the presence of specific magic liquids beneath it. When the required liquid is detected, the teleporter activates, transporting the player to a predefined location.

## Key Components

### `TeleportComponent`

This component handles the core teleportation logic.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `_tags="enabled_by_liquid"` | Ensures this component is only active when the teleporter is powered.       |
| `target_x_is_absolute_position="1"` | Indicates that `target.x` and `target.y` specify absolute world coordinates. |
| `target.x="-677"`     | The absolute X-coordinate to teleport to.                                   |
| `target.y="280"`      | The absolute Y-coordinate to teleport to.                                   |

### `HitboxComponent`

Defines the physical boundaries of the teleporter.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `_tags="enabled_by_liquid"` | Active when the teleporter is powered.    |
| `aabb_min_x="-15"` | Minimum X-axis bounding box coordinate.   |
| `aabb_min_y="-15"` | Minimum Y-axis bounding box coordinate.   |
| `aabb_max_x="15"`  | Maximum X-axis bounding box coordinate.   |
| `aabb_max_y="15"`  | Maximum Y-axis bounding box coordinate.   |

### `UIInfoComponent`

Provides information for the user interface.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `_tags="enabled_by_liquid"` | Active when the teleporter is powered.    |
| `name="$teleport_deeper"` | The in-game name displayed for this teleporter. |

### `LightComponent`

Adds visual lighting effects to the teleporter.

| Attribute       | Description                                                                 |
| :-------------- | :-------------------------------------------------------------------------- |
| `_tags="enabled_by_liquid"` | Active when the teleporter is powered.                                      |
| `_enabled="1"`  | Enables the light component.                                                |
| `radius="255"`  | The radius of the light effect.                                             |
| `fade_out_time="1.5"` | The time in seconds for the light to fade out.                              |
| `r="64"`, `g="100"`, `b="255"` | The RGB color values of the light.                                          |
| `offset_y="-16"` | Vertical offset for the light's position.                                   |

*Note: There are two `LightComponent` instances, likely for different visual layers or effects.*

### `ParticleEmitterComponent`

Generates visual particle effects.

| Attribute                  | Description                                                                 |
| :------------------------- | :-------------------------------------------------------------------------- |
| `_tags="enabled_by_liquid"` | Active when the teleporter is powered.                                      |
| `emitted_material_name="spark_purple"` | The material of the particles being emitted.                                |
| `gravity.y="0.0"`          | No vertical gravity applied to particles.                                   |
| `lifetime_min="3"`, `lifetime_max="4"` | The minimum and maximum lifespan of particles in seconds.                   |
| `x_vel_min="0"`, `x_vel_max="0"` | No horizontal velocity.                                                     |
| `y_vel_min="0"`, `y_vel_max="0"` | No vertical velocity.                                                       |
| `count_min="115"`, `count_max="115"` | The number of particles emitted per interval.                               |
| `render_on_grid="1"`       | Particles are rendered on the game grid.                                    |
| `area_circle_radius.min="15"`, `area_circle_radius.max="15"` | Particles are emitted within a circular area.                               |
| `cosmetic_force_create="1"` | Particles are created as cosmetic effects.                                  |
| `velocity_always_away_from_center="11"` | Particles are pushed away from the emitter's center.                        |

*Note: There are two `ParticleEmitterComponent` instances, likely for different visual effects or densities.*

### `SpriteComponent`

Defines the visual appearance of the teleporter.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `_tags="enabled_by_liquid"` | Active when the teleporter is powered.    |
| `image_file="data/buildings_gfx/teleport_center.xml"` | The sprite image file.                    |
| `z_index="1"` | Rendering layer.                          |
| `additive="1"` | Uses additive blending for rendering.     |

### `AudioLoopComponent`

Plays looping sound effects when the teleporter is active.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `_tags="enabled_by_liquid"` | Active when the teleporter is powered.                                      |
| `file="data/audio/Desktop/misc.bank"` | The audio bank file.                                                        |
| `event_name="misc/teleport_loop"` | The specific audio event to play.                                           |
| `auto_play_if_enabled="1"` | Automatically plays when the component is enabled.                          |
| `play_on_component_enable="1"` | Plays the sound when this component is enabled.                             |

*Note: There are two `AudioLoopComponent` instances, likely for different sound loops.*

### `MaterialAreaCheckerComponent`

This component is crucial for detecting the presence of specific liquids beneath the teleporter.

| Attribute                                | Description                                                                                             |
| :--------------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `area_aabb.min_x="-2"`, `area_aabb.max_x="2"` | Defines the X-axis bounds of the detection area relative to the teleporter's center.                    |
| `area_aabb.min_y="136"`, `area_aabb.max_y="140"` | Defines the Y-axis bounds of the detection area relative to the teleporter's center.                    |
| `update_every_x_frame="60"`              | How often the area is checked (every 60 frames).                                                        |
| `material="magic_liquid_teleportation"`  | The primary magic liquid to detect.                                                                     |
| `material2="magic_liquid_unstable_teleportation"` | An alternative magic liquid that can also activate the teleporter.                                      |
| `look_for_failure="1"`                   | When set to 1, this checker looks for the *absence* of the specified materials (used for deactivation). |
| `look_for_failure="0"`                   | When set to 0, this checker looks for the *presence* of the specified materials (used for activation). |
| `kill_after_message="0"`                 | Prevents the entity from being destroyed after a message is sent.                                       |

*Note: Two `MaterialAreaCheckerComponent` instances are used: one to detect the presence of the required liquids for activation, and another to detect their absence for deactivation.*

### `LuaComponent`

Links the `MaterialAreaCheckerComponent` to specific Lua scripts for handling detection results.

| Attribute                                | Description                                                                 |
| :--------------------------------------- | :-------------------------------------------------------------------------- |
| `script_material_area_checker_failed="data/scripts/buildings/teleport_liquid_check.lua"` | The script to run when the material check fails (liquid is absent).         |
| `script_material_area_checker_success="data/scripts/buildings/teleport_liquid_check.lua"` | The script to run when the material check succeeds (liquid is present).     |