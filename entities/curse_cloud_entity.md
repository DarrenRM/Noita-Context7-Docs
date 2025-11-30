---
title: Curse Cloud Entity
category: entities
---

# Curse Cloud Entity

This entity defines the visual and functional aspects of a curse cloud in Noita. It utilizes several `ParticleEmitterComponent`s to create its visual appearance and `GameEffectComponent` and `LuaComponent`s to handle its gameplay effects.

## Core Components

### GameEffectComponent

This component defines the primary game effect associated with the entity.

| Attribute           | Value        | Description                                                                 |
| :------------------ | :----------- | :-------------------------------------------------------------------------- |
| `effect`            | `CUSTOM`     | Indicates a custom effect is being applied.                                 |
| `custom_effect_id`  | `CURSE_CLOUD_01` | A unique identifier for this specific curse cloud effect.                   |
| `frames`            | `-1`         | The duration of the effect. `-1` typically means it's indefinite or persistent. |

### ParticleEmitterComponent (Multiple)

These components are responsible for generating the visual particles that make up the curse cloud.

#### Particle Emitter 1 (Water)

This emitter creates the base "water" particles for the cloud.

| Attribute                 | Value                                     | Description                                                                 |
| :------------------------ | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `water`                                   | The material of the particles being emitted.                                |
| `offset.y`                | `-42`                                     | Vertical offset of the emitter.                                             |
| `count_min`               | `1`                                       | Minimum number of particles emitted per interval.                           |
| `count_max`               | `2`                                       | Maximum number of particles emitted per interval.                           |
| `emission_interval_min_frames` | `3`                                       | Minimum frames between emissions.                                           |
| `emission_interval_max_frames` | `6`                                       | Maximum frames between emissions.                                           |
| `image_animation_file`    | `data/particles/image_emitters/cloud_bottom.png` | The sprite sheet used for the particle animation.                           |
| `create_real_particles`   | `1`                                       | Indicates that these are actual game particles, not just cosmetic ones.     |

#### Particle Emitter 2 (Smoke - Cosmetic)

This emitter generates cosmetic smoke particles for a softer cloud appearance.

| Attribute                 | Value                                 | Description                                                                 |
| :------------------------ | :------------------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `smoke`                               | The material of the particles being emitted.                                |
| `offset.y`                | `-45`                                 | Vertical offset of the emitter.                                             |
| `x_pos_offset_min`        | `-1`                                  | Minimum horizontal offset for particle spawn.                               |
| `x_pos_offset_max`        | `1`                                   | Maximum horizontal offset for particle spawn.                               |
| `y_pos_offset_min`        | `-1`                                  | Minimum vertical offset for particle spawn.                                 |
| `y_pos_offset_max`        | `1`                                   | Maximum vertical offset for particle spawn.                                 |
| `lifetime_min`            | `0.2`                                 | Minimum lifetime of the particles in seconds.                               |
| `lifetime_max`            | `0.5`                                 | Maximum lifetime of the particles in seconds.                               |
| `emission_interval_min_frames` | `10`                                  | Minimum frames between emissions.                                           |
| `emission_interval_max_frames` | `10`                                  | Maximum frames between emissions.                                           |
| `image_animation_file`    | `data/particles/image_emitters/cloud.png` | The sprite sheet used for the particle animation.                           |
| `emit_cosmetic_particles` | `1`                                   | Indicates these are cosmetic particles, primarily for visual effect.        |
| `create_real_particles`   | `0`                                   | These are not real game particles that interact with the environment.       |
| `is_emitting`             | `0`                                   | This emitter is initially set to not emit.                                  |

#### Particle Emitter 3 (Smoke - Real)

This emitter generates real smoke particles that can interact with the game world.

| Attribute                 | Value                                 | Description                                                                 |
| :------------------------ | :------------------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `smoke`                               | The material of the particles being emitted.                                |
| `offset.y`                | `-45`                                 | Vertical offset of the emitter.                                             |
| `lifetime_min`            | `0.2`                                 | Minimum lifetime of the particles in seconds.                               |
| `lifetime_max`            | `0.5`                                 | Maximum lifetime of the particles in seconds.                               |
| `emission_interval_min_frames` | `1`                                   | Minimum frames between emissions.                                           |
| `emission_interval_max_frames` | `10`                                  | Maximum frames between emissions.                                           |
| `image_animation_file`    | `data/particles/image_emitters/cloud.png` | The sprite sheet used for the particle animation.                           |
| `create_real_particles`   | `1`                                   | These are real game particles that interact with the environment.           |
| `is_emitting`             | `0`                                   | This emitter is initially set to not emit.                                  |

#### Particle Emitter 4 (Spark Red - Cosmetic)

This emitter creates cosmetic red sparks, likely for visual flair.

| Attribute                 | Value                                     | Description                                                                 |
| :------------------------ | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_red`                               | The material of the particles being emitted.                                |
| `offset.y`                | `-45`                                     | Vertical offset of the emitter.                                             |
| `y_pos_offset_min`        | `7`                                       | Minimum vertical offset for particle spawn.                                 |
| `y_pos_offset_max`        | `7`                                       | Maximum vertical offset for particle spawn.                                 |
| `lifetime_min`            | `0.06`                                    | Minimum lifetime of the particles in seconds.                               |
| `lifetime_max`            | `0.12`                                    | Maximum lifetime of the particles in seconds.                               |
| `airflow_force`           | `0.015`                                   | Force applied by airflow to the particles.                                  |
| `airflow_scale`           | `0.01`                                    | Scale of the airflow effect.                                                |
| `airflow_time`            | `0.1`                                     | Duration of the airflow effect.                                             |
| `image_animation_file`    | `data/particles/image_emitters/cloud_outline.png` | The sprite sheet used for the particle animation.                           |
| `cosmetic_force_create`   | `1`                                       | Forces the creation of cosmetic particles.                                  |
| `collide_with_grid`       | `0`                                       | Particles do not collide with the game grid.                                |
| `create_real_particles`   | `0`                                       | These are not real game particles.                                          |

#### Particle Emitter 5 (Spark Red - Real)

This emitter creates real red sparks that can interact with the game world.

| Attribute                 | Value                                     | Description                                                                 |
| :------------------------ | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_red`                               | The material of the particles being emitted.                                |
| `offset.y`                | `-45`                                     | Vertical offset of the emitter.                                             |
| `y_pos_offset_min`        | `7`                                       | Minimum vertical offset for particle spawn.                                 |
| `y_pos_offset_max`        | `7`                                       | Maximum vertical offset for particle spawn.                                 |
| `lifetime_min`            | `2.5`                                     | Minimum lifetime of the particles in seconds.                               |
| `lifetime_max`            | `3.8`                                     | Maximum lifetime of the particles in seconds.                               |
| `airflow_force`           | `0.15`                                    | Force applied by airflow to the particles.                                  |
| `airflow_scale`           | `0.1`                                     | Scale of the airflow effect.                                                |
| `airflow_time`            | `0.1`                                     | Duration of the airflow effect.                                             |
| `image_animation_file`    | `data/particles/image_emitters/cloud_outline.png` | The sprite sheet used for the particle animation.                           |
| `cosmetic_force_create`   | `0`                                       | This is not a forced cosmetic particle creation.                            |
| `emission_interval_min_frames` | `15`                                      | Minimum frames between emissions.                                           |
| `emission_interval_max_frames` | `60`                                      | Maximum frames between emissions.                                           |
| `create_real_particles`   | `0`                                       | These are not real game particles.                                          |

### LuaComponent (Thunder Effect)

This component links to a Lua script that handles a thunder effect associated with the curse cloud.

| Attribute             | Value                                          | Description                                                                 |
| :-------------------- | :--------------------------------------------- | :-------------------------------------------------------------------------- |
| `script_source_file`  | `data/scripts/status_effects/effect_curse_cloud_thunder.lua` | Path to the Lua script file.                                                |
| `execute_every_n_frame` | `250`                                          | The script will execute every 250 frames.                                   |

### LuaComponent (Main Curse Effect)

This component links to the primary Lua script that governs the curse cloud's behavior.

| Attribute             | Value                                     | Description                                                                 |
| :-------------------- | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `_tags`               | `curse_cloud_script`                      | A tag for identifying this script.                                          |
| `script_source_file`  | `data/scripts/status_effects/effect_curse_cloud.lua` | Path to the Lua script file.                                                |
| `execute_every_n_frame` | `1`                                       | The script will execute every frame, allowing for continuous updates.       |

### AudioComponent

This component handles the sound effects associated with the curse cloud.

| Attribute    | Value                               | Description                                                                 |
| :----------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `file`       | `data/audio/Desktop/projectiles.bank` | The audio bank file containing the sound events.                            |
| `event_root` | `player_projectiles/cloud`          | The root event name for sounds related to this cloud.                       |