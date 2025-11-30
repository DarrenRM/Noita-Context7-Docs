---
title: Critical Hit Projectile Particle Emitter
category: entities
---

# Critical Hit Projectile Particle Emitter

This entity defines the particle effects that are emitted when a critical hit occurs with a projectile in Noita. It utilizes a `ParticleEmitterComponent` to generate visual sparks.

## Key Attributes of `ParticleEmitterComponent`

| Attribute                 | Description                                                                                                |
| :------------------------ | :--------------------------------------------------------------------------------------------------------- |
| `emitted_material_name`   | The material name of the particles to be emitted. Here, it's "spark_red".                                  |
| `x_pos_offset_min`/`max` | The minimum and maximum horizontal offset for particle emission.                                           |
| `y_pos_offset_min`/`max` | The minimum and maximum vertical offset for particle emission.                                             |
| `gravity.y`               | The gravitational force applied to the particles in the Y-axis. Set to "0" for no gravity.                 |
| `x_vel_min`/`max`         | The minimum and maximum horizontal velocity of emitted particles.                                          |
| `y_vel_min`/`max`         | The minimum and maximum vertical velocity of emitted particles.                                            |
| `count_min`/`max`         | The minimum and maximum number of particles emitted per emission cycle.                                    |
| `is_trail`                | If set to "1", particles will leave a trail.                                                               |
| `trail_gap`               | The spacing between particles in a trail.                                                                  |
| `fade_based_on_lifetime`  | If set to "1", particles will fade out as their lifetime decreases.                                        |
| `lifetime_min`/`max`      | The minimum and maximum lifetime of individual particles in seconds.                                       |
| `airflow_force`           | The strength of the airflow effect on particles.                                                           |
| `airflow_time`            | The duration for which airflow affects particles.                                                          |
| `airflow_scale`           | The scaling factor for the airflow effect.                                                                 |
| `create_real_particles`   | If set to "0", these are cosmetic particles and do not interact physically.                                |
| `emit_cosmetic_particles` | If set to "1", these particles are purely visual.                                                          |
| `emission_interval_min_frames`/`max_frames` | The minimum and maximum number of frames between particle emission events. |
| `is_emitting`             | If set to "1", the emitter is active.                                                                      |