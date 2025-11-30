---
title: Tiny Spark (Blue, Large) Particle Emitter
category: entities
---

# Tiny Spark (Blue, Large) Particle Emitter

This entity defines a particle emitter that generates small, blue sparks. It's designed to be a cosmetic effect, not a physical entity.

## Key Components

### ParticleEmitterComponent

This is the core component responsible for generating and managing the particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles to be emitted (e.g., `spark_blue_dark`).      |
| `x_pos_offset_min`/`max` | The minimum and maximum horizontal offset from the emitter's origin.        |
| `y_pos_offset_min`/`max` | The minimum and maximum vertical offset from the emitter's origin.          |
| `gravity.y`               | The vertical gravitational force applied to the particles. `0` means no gravity. |
| `x_vel_min`/`max`         | The minimum and maximum horizontal velocity of emitted particles.           |
| `y_vel_min`/`max`         | The minimum and maximum vertical velocity of emitted particles.             |
| `count_min`/`max`         | The minimum and maximum number of particles emitted per emission cycle.     |
| `lifetime_min`/`max`      | The minimum and maximum lifetime of individual particles in seconds.        |
| `airflow_force`           | The strength of the airflow effect on particles.                            |
| `airflow_time`            | The duration for which airflow affects particles.                           |
| `airflow_scale`           | The scaling factor for the airflow effect.                                  |
| `create_real_particles`   | If `0`, these are cosmetic particles and don't interact physically.         |
| `emit_cosmetic_particles` | If `1`, particles are rendered as cosmetic effects.                         |
| `emission_interval_min_frames`/`max_frames` | The minimum and maximum frames between particle emissions. |
| `is_emitting`             | If `1`, the emitter is active.                                              |

### LifetimeComponent

This component defines the overall lifetime of the entity itself.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The total lifetime of the emitter in seconds. |