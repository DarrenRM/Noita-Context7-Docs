---
title: Tiny Green Spark Emitter (Sparse)
category: entities
---

# Tiny Green Spark Emitter (Sparse)

This entity defines a sparse emitter for small, green sparks. It's designed to create cosmetic particles rather than real ones, meaning they don't interact physically with the game world.

## Key Components

### ParticleEmitterComponent

This is the core component responsible for generating the particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles to be emitted. Set to `spark_green`.          |
| `x_pos_offset_min`/`max` | Defines the horizontal spread of the emission point.                        |
| `y_pos_offset_min`/`max` | Defines the vertical spread of the emission point.                          |
| `gravity.y`               | The gravitational pull on the emitted particles. Set to `0` for no gravity. |
| `x_vel_min`/`max`         | The minimum and maximum horizontal velocity of emitted particles.           |
| `y_vel_min`/`max`         | The minimum and maximum vertical velocity of emitted particles.             |
| `count_min`/`max`         | The number of particles emitted per burst.                                  |
| `lifetime_min`/`max`      | The duration (in seconds) each particle exists.                             |
| `airflow_force`           | The strength of airflow affecting particles.                                |
| `airflow_time`            | How long airflow affects particles.                                         |
| `airflow_scale`           | The scaling factor for airflow.                                             |
| `create_real_particles`   | Set to `0` to emit cosmetic particles only.                                 |
| `emit_cosmetic_particles` | Set to `1` to ensure cosmetic particles are emitted.                        |
| `emission_interval_min_frames`/`max_frames` | The delay between particle emission bursts in frames. |
| `is_emitting`             | Set to `1` to enable emission.                                              |