---
title: Ominous Orb Entity
category: entities
---

# Ominous Orb Entity

This document describes the `ominous_orb.xml` entity, which represents a special building in Noita. It's designed to interact with the player and emit visual effects.

## Core Components

The `ominous_orb` entity is primarily defined by its interaction and visual components.

### `CollisionTriggerComponent`

This component defines the area around the orb that triggers an event when the player enters it.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `width`                   | `128`   | The width of the collision box.                                             |
| `height`                  | `128`   | The height of the collision box.                                            |
| `radius`                  | `64`    | The radius of the circular collision area.                                  |
| `required_tag`            | `player_unit` | The entity tag that must be present to trigger the collision (i.e., the player). |
| `destroy_this_entity_when_triggered` | `0`     | Indicates that the orb should not be destroyed when triggered.              |

### `LuaComponent`

This component links the collision trigger to a specific Lua script that handles the orb's behavior.

| Attribute                 | Value                                  | Description                                                                 |
| :------------------------ | :------------------------------------- | :-------------------------------------------------------------------------- |
| `script_collision_trigger_hit` | `data/scripts/buildings/ominous_orb.lua` | The path to the Lua script executed when the `CollisionTriggerComponent` is hit. |
| `execute_every_n_frame`   | `-1`                                   | This means the script is executed only once when the trigger is hit.        |

### `LightComponent`

This component defines the light emitted by the orb, contributing to its visual presence.

| Attribute | Value | Description                                     |
| :-------- | :---- | :---------------------------------------------- |
| `radius`  | `64`  | The radius of the light's influence.            |
| `r`       | `200` | The red component of the light's color (0-255). |
| `g`       | `200` | The green component of the light's color (0-255). |
| `b`       | `200` | The blue component of the light's color (0-255).  |
| `fade_out_time` | `0.2` | The time it takes for the light to fade out.    |

## Particle Emitters

The orb utilizes two `ParticleEmitterComponent`s to create visual effects.

### Inner Particle Emitter

This emitter is responsible for particles that appear closer to the orb's center.

| Attribute                 | Value          | Description                                                                 |
| :------------------------ | :------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_blue_dark` | The material of the particles being emitted.                                |
| `gravity.y`               | `0.0`          | No vertical gravity applied to these particles.                             |
| `lifetime_min`            | `0.5`          | Minimum lifetime of emitted particles in seconds.                           |
| `lifetime_max`            | `1.0`          | Maximum lifetime of emitted particles in seconds.                           |
| `count_min`               | `4`            | Minimum number of particles emitted per emission.                           |
| `count_max`               | `7`            | Maximum number of particles emitted per emission.                           |
| `render_on_grid`          | `1`            | Particles are rendered on the game grid.                                    |
| `fade_based_on_lifetime`  | `1`            | Particles fade out as their lifetime decreases.                             |
| `area_circle_radius.max`  | `64`           | The maximum radius of the area from which particles are emitted.            |
| `cosmetic_force_create`   | `0`            | Particles are not purely cosmetic and can interact.                         |
| `airflow_force`           | `0.5`          | The force applied by airflow to the particles.                              |
| `airflow_time`            | `0.01`         | The duration airflow affects particles.                                     |
| `airflow_scale`           | `0.05`         | The scaling factor for airflow effects.                                     |
| `emission_interval_min_frames` | `1`            | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `1`            | Maximum frames between particle emissions.                                  |
| `emit_cosmetic_particles` | `1`            | Emits cosmetic particles.                                                   |
| `is_emitting`             | `1`            | The emitter is active.                                                      |
| `draw_as_long`            | `1`            | Particles are drawn for their full lifetime.                                |
| `attractor_force`         | `7`            | Particles are attracted towards a point with this force.                    |

### Outer Ring Particle Emitter

This emitter creates particles forming an outer ring effect.

| Attribute                 | Value          | Description                                                                 |
| :------------------------ | :------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_blue_dark` | The material of the particles being emitted.                                |
| `gravity.y`               | `0.0`          | No vertical gravity applied to these particles.                             |
| `lifetime_min`            | `0.2`          | Minimum lifetime of emitted particles in seconds.                           |
| `lifetime_max`            | `0.8`          | Maximum lifetime of emitted particles in seconds.                           |
| `count_min`               | `7`            | Minimum number of particles emitted per emission.                           |
| `count_max`               | `12`           | Maximum number of particles emitted per emission.                           |
| `render_on_grid`          | `1`            | Particles are rendered on the game grid.                                    |
| `fade_based_on_lifetime`  | `1`            | Particles fade out as their lifetime decreases.                             |
| `area_circle_radius.min`  | `64`           | The minimum radius of the area from which particles are emitted.            |
| `area_circle_radius.max`  | `64`           | The maximum radius of the area from which particles are emitted.            |
| `cosmetic_force_create`   | `0`            | Particles are not purely cosmetic and can interact.                         |
| `airflow_force`           | `0.3`          | The force applied by airflow to the particles.                              |
| `airflow_time`            | `0.01`         | The duration airflow affects particles.                                     |
| `airflow_scale`           | `0.05`         | The scaling factor for airflow effects.                                     |
| `emission_interval_min_frames` | `1`            | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `1`            | Maximum frames between particle emissions.                                  |
| `emit_cosmetic_particles` | `1`            | Emits cosmetic particles.                                                   |
| `is_emitting`             | `1`            | The emitter is active.                                                      |