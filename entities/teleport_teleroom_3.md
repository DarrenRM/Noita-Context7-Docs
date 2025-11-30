---
title: Teleport Teleroom 3
category: entities
---

# Teleport Teleroom 3

This entity defines a specific type of teleporter, likely a decorative or functional element within a "teleroom" in Noita. It utilizes a combination of components to achieve its teleportation effect, visual feedback, and sound.

## Key Components and Attributes

### TeleportComponent

This is the core component responsible for the teleportation functionality.

| Attribute   | Value       | Description                                                                 |
| :---------- | :---------- | :-------------------------------------------------------------------------- |
| `target.x`  | `-13624`    | The X-coordinate of the teleportation destination.                          |
| `target.y`  | `-13824`    | The Y-coordinate of the teleportation destination.                          |
| `_tags`     | `enabled_by_liquid` | This teleporter is activated or enabled when submerged in liquid. |

### HitboxComponent

Defines the physical boundaries of the teleporter.

| Attribute   | Value   | Description                                                                 |
| :---------- | :------ | :-------------------------------------------------------------------------- |
| `aabb_min_x`| `-15`   | Minimum X-coordinate of the bounding box.                                   |
| `aabb_min_y`| `-15`   | Minimum Y-coordinate of the bounding box.                                   |
| `aabb_max_x`| `15`    | Maximum X-coordinate of the bounding box.                                   |
| `aabb_max_y`| `15`    | Maximum Y-coordinate of the bounding box.                                   |
| `_tags`     | `enabled_by_liquid` | The hitbox is also affected by the liquid state.                        |

### LightComponent

Adds visual illumination to the teleporter. There are two `LightComponent` instances, likely for different visual effects or layers of light.

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `radius`        | `255`   | The radius of the light's influence.                                        |
| `fade_out_time` | `1.5`   | How long it takes for the light to fade out.                                |
| `r`, `g`, `b`   | `64`, `100`, `255` | RGB color values for the light (a bluish hue).                            |
| `offset_y`      | `-16`   | Vertical offset for the light's position.                                   |
| `_tags`         | `enabled_by_liquid` | The light is active when submerged in liquid.                           |

### SpriteParticleEmitterComponent

Generates visual particles that swirl around the teleporter, creating a dynamic effect.

| Attribute               | Value        | Description                                                                 |
| :---------------------- | :----------- | :-------------------------------------------------------------------------- |
| `sprite_file`           | `data/particles/redwhirl_$[1-8].png` | Uses a sequence of sprites for animated particle visuals.                 |
| `lifetime`              | `1.5`        | Duration each particle exists.                                              |
| `color_change.a`        | `-0.8`       | Alpha value decreases over time, causing particles to fade out.             |
| `angular_velocity`      | `7.5`        | Speed at which particles rotate.                                            |
| `scale_velocity.x/y`    | `1.0075`     | Particles slightly grow over time.                                          |
| `emission_interval_min/max_frames` | `2`/`4`      | Controls the rate of particle emission.                                     |
| `randomize_position`    | `-0.5` to `0.5` | Particles are emitted within a small random area.                           |
| `randomize_velocity`    | `-5` to `5`  | Particles have a slight random initial velocity.                            |
| `_tags`                 | `enabled_by_liquid` | Particle emission is tied to being in liquid.                             |

### ParticleEmitterComponent (x2)

These components emit "spark_red" particles, contributing to the visual flair of the teleporter. The two instances likely create different densities or behaviors of sparks.

| Attribute                   | Value        | Description                                                                 |
| :-------------------------- | :----------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`     | `spark_red`  | The type of particle being emitted.                                         |
| `gravity.y`                 | `0.0`        | Particles are not affected by gravity.                                      |
| `lifetime_min/max`          | `3`/`4`      | Duration each spark exists.                                                 |
| `count_min/max`             | `75`/`115` (first) / `1`/`1` (second) | Controls the number of sparks emitted. The first is a dense burst, the second is sparse. |
| `area_circle_radius.min/max`| `15`/`15` (first) / `0`/`15` (second) | Defines the area from which sparks are emitted.                           |
| `airflow_force/time/scale`  | `0.051`/`1.01`/`0.03` | Parameters related to how particles interact with airflow.                  |
| `velocity_always_away_from_center` | `11` (first) / `0` (second) | The first emitter pushes sparks away from the center, the second does not. |
| `_tags`                     | `enabled_by_liquid` | Spark emission is active when in liquid.                                  |

### LuaComponent

This component links the entity to a Lua script that handles more complex logic, such as the teleporter's activation and behavior.

| Attribute           | Value                           | Description                                                                 |
| :------------------ | :------------------------------ | :-------------------------------------------------------------------------- |
| `script_source_file`| `data/scripts/buildings/teleroom.lua` | The path to the Lua script controlling the teleporter's behavior.           |
| `execute_every_n_frame` | `50`                            | The script logic is executed every 50 frames.                               |

### AudioLoopComponent (x2)

These components are responsible for playing looping sound effects associated with the teleporter.

| Attribute           | Value                           | Description                                                                 |
| :------------------ | :------------------------------ | :-------------------------------------------------------------------------- |
| `file`              | `data/audio/Desktop/misc.bank`  | The audio bank containing the sound events.                                 |
| `event_name`        | `misc/teleport_end_loop` / `misc/teleport_end_emitter_loop` | The specific sound events to be played.                                     |
| `auto_play_if_enabled` | `1`                             | The sound will automatically play if the component is enabled.              |
| `play_on_component_enable` | `1`                             | The sound will play when the component is enabled.                          |
| `_tags`             | `enabled_by_liquid`             | Audio playback is tied to being in liquid.                                  |