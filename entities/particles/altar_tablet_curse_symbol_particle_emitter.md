---
title: Altar Tablet Curse Symbol Particle Emitter
category: entities/particles
---

# Altar Tablet Curse Symbol Particle Emitter

This entity defines a particle emitter that creates a visual effect resembling a curse symbol, likely used in conjunction with altars or similar game mechanics.

## Key Components

### ParticleEmitterComponent

This component governs the behavior and appearance of the emitted particles.

| Attribute                 | Value      | Description                                                                 |
| :------------------------ | :--------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_red`| The material/type of particle to be emitted.                                |
| `gravity.y`               | `0.0`      | No vertical gravity applied to the particles.                               |
| `lifetime_min`            | `3`        | Minimum lifetime of each individual particle in seconds.                    |
| `lifetime_max`            | `8`        | Maximum lifetime of each individual particle in seconds.                    |
| `count_min`               | `4`        | Minimum number of particles emitted per emission.                           |
| `count_max`               | `4`        | Maximum number of particles emitted per emission.                           |
| `render_on_grid`          | `1`        | Particles will be rendered even when the game camera is zoomed out.         |
| `fade_based_on_lifetime`  | `1`        | Particles will fade out as their lifetime decreases.                        |
| `area_circle_radius.min`  | `0`        | Minimum radius of the emission area (a circle).                             |
| `area_circle_radius.max`  | `0`        | Maximum radius of the emission area. This results in a single point emission. |
| `cosmetic_force_create`   | `0`        | Particles are not forced to be created if the game is in a cosmetic-only mode. |
| `airflow_force`           | `0.251`    | The strength of airflow affecting the particles.                            |
| `airflow_time`            | `1.01`     | The duration airflow affects the particles.                                 |
| `airflow_scale`           | `0.05`     | The scaling factor for airflow.                                             |
| `emission_interval_min_frames` | `1`    | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `1`    | Maximum frames between particle emissions.                                  |
| `emit_cosmetic_particles` | `1`        | Emits cosmetic particles.                                                   |
| `image_animation_file`    | `magic_effect_1.png` | The image file used for particle animation.                               |
| `image_animation_speed`   | `2`        | Speed of the image animation.                                               |
| `image_animation_loop`    | `0`        | The animation does not loop.                                                |
| `is_emitting`             | `1`        | The particle emitter is active.                                             |

### LifetimeComponent

This component defines the overall lifetime of the entity itself.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `260` | The total lifetime of this entity in seconds. |