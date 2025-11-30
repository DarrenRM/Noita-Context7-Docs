---
title: Tiny Green Spark Trail Particle
category: entities
---

# Tiny Green Spark Trail Particle

This entity defines a particle effect that creates a trail of small green sparks. It's designed to be attached to other entities to provide a visual trail.

## Key Components

### ParticleEmitterComponent

This component handles the emission of particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles to be emitted (e.g., `spark_green`).          |
| `x_pos_offset_min`/`max`  | Minimum and maximum X-axis offset for particle emission.                    |
| `y_pos_offset_min`/`max`  | Minimum and maximum Y-axis offset for particle emission.                    |
| `gravity.y`               | The Y-axis gravity applied to emitted particles. `0` means no gravity.      |
| `x_vel_min`/`max`         | Minimum and maximum X-axis velocity for emitted particles.                  |
| `y_vel_min`/`max`         | Minimum and maximum Y-axis velocity for emitted particles.                  |
| `count_min`/`max`         | The minimum and maximum number of particles emitted per emission cycle.     |
| `is_trail`                | If `1`, particles are emitted as a trail.                                   |
| `trail_gap`               | The spacing between particles in a trail.                                   |
| `fade_based_on_lifetime`  | If `1`, particles fade out as their lifetime decreases.                     |
| `lifetime_min`/`max`      | The minimum and maximum lifetime of individual emitted particles.           |
| `airflow_force`           | The force of airflow affecting particles.                                   |
| `airflow_time`            | The duration for which airflow affects particles.                           |
| `airflow_scale`           | The scale of the airflow effect.                                            |
| `create_real_particles`   | If `0`, these are cosmetic particles and don't interact physically.         |
| `emit_cosmetic_particles` | If `1`, cosmetic particles are emitted.                                     |
| `render_on_grid`          | If `1`, particles are rendered on the game grid.                            |
| `emission_interval_min_frames`/`max_frames` | The interval (in frames) between particle emissions. |
| `is_emitting`             | If `1`, the emitter is active.                                              |

### LifetimeComponent

This component defines the lifetime of the entity itself.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The total lifetime of this entity in seconds. |