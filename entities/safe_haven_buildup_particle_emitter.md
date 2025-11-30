---
title: Safe Haven Buildup Particle Emitter
category: data/entities/particles
---

# Safe Haven Buildup Particle Emitter

This entity defines a particle emitter responsible for creating visual effects associated with the "Safe Haven" buildup in Noita. It's designed to emit green sparks with specific lifetime and emission properties.

## Key Components and Attributes

### ParticleEmitterComponent

This is the core component responsible for generating and managing the particles.

| Attribute                  | Value     | Description                                                                 |
| :------------------------- | :-------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`    | `spark_green` | The material of the particles being emitted.                                |
| `gravity.y`                | `0.0`     | No vertical gravity applied to the emitted particles.                       |
| `offset.y`                 | `-18`     | Vertical offset for particle emission.                                      |
| `lifetime_min`             | `4`       | Minimum lifetime of each emitted particle in seconds.                       |
| `lifetime_max`             | `8`       | Maximum lifetime of each emitted particle in seconds.                       |
| `count_min`                | `8`       | Minimum number of particles emitted per emission interval.                  |
| `count_max`                | `8`       | Maximum number of particles emitted per emission interval.                  |
| `render_on_grid`           | `1`       | Particles are rendered on the game grid.                                    |
| `collide_with_grid`        | `0`       | Particles do not collide with the game grid.                                |
| `collide_with_gas_and_fire`| `0`       | Particles do not collide with gas or fire.                                  |
| `fade_based_on_lifetime`   | `1`       | Particles fade out as their lifetime decreases.                             |
| `area_circle_radius.min`   | `0`       | Minimum radius of the emission area (a single point).                       |
| `area_circle_radius.max`   | `0`       | Maximum radius of the emission area (a single point).                       |
| `emission_interval_min_frames` | `1`   | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `1`   | Maximum frames between particle emissions.                                  |
| `emit_cosmetic_particles`  | `1`       | Emits cosmetic particles, which are purely visual.                          |
| `image_animation_file`     | `data/particles/image_emitters/safe_haven_emitter.png` | Path to the image animation sprite sheet for the particles. |
| `image_animation_speed`    | `2`       | Speed of the image animation.                                               |
| `image_animation_loop`     | `0`       | The image animation does not loop.                                          |
| `is_emitting`              | `1`       | The emitter is active and emitting particles.                               |

### LifetimeComponent

Determines the overall lifetime of the entity itself.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `260` | The entity will exist for 260 seconds.    |

### AudioLoopComponent

Plays a looping sound effect associated with this entity.

| Attribute     | Value                     | Description                                     |
| :------------ | :------------------------ | :---------------------------------------------- |
| `file`        | `data/audio/Desktop/misc.bank` | The audio bank containing the sound event.      |
| `event_name`  | `misc/runestone_loop`     | The name of the sound event to play.            |
| `auto_play`   | `1`                       | The sound effect starts playing automatically.  |