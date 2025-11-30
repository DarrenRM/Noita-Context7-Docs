---
title: Green Sparse Poof Particle
category: data/entities
---

# Green Sparse Poof Particle

This entity defines a particle effect that creates a sparse green poof. It's primarily used for visual feedback, such as when certain spells or events occur.

## Key Components

### ProjectileComponent

This component defines the projectile-like behavior of the entity. In this case, it's configured to primarily act as a container for the particle emitter and to manage its lifetime.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `_enabled`                | `1`     | Enables the component.                                                      |
| `speed_min`, `speed_max`  | `0`     | The projectile has no initial velocity.                                     |
| `die_on_low_velocity`     | `0`     | The projectile does not die when its velocity becomes low.                  |
| `on_death_explode`        | `0`     | The projectile does not explode upon death.                                 |
| `on_death_gfx_leave_sprite` | `0`     | No graphical effect is left behind when the projectile dies.                |
| `on_lifetime_out_explode` | `1`     | The projectile will explode when its lifetime runs out.                     |
| `on_collision_die`        | `0`     | The projectile does not die upon collision.                                 |
| `damage`                  | `0`     | The projectile deals no damage.                                             |
| `lifetime`                | `5`     | The projectile exists for 5 seconds before its lifetime runs out.           |

#### `config_explosion`

This nested configuration defines the explosion that occurs when the projectile's lifetime ends.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `never_cache`             | `1`     | Prevents caching of this explosion configuration.                             |
| `damage`                  | `0`     | The explosion deals no damage.                                              |
| `camera_shake`            | `0`     | No camera shake is applied.                                                 |
| `explosion_radius`        | `0`     | The explosion has no radius.                                                |
| `explosion_sprite`        | `""`    | No specific sprite is used for the explosion.                               |
| `explosion_sprite_lifetime` | `0`     | The explosion sprite has no defined lifetime.                               |
| `create_cell_material`    | `""`    | No material is created by the explosion.                                    |
| `create_cell_probability` | `0`     | No probability of creating material.                                        |
| `hole_destroy_liquid`     | `0`     | The explosion does not destroy liquids.                                     |
| `hole_enabled`            | `0`     | No holes are created by the explosion.                                      |
| `particle_effect`         | `0`     | No specific particle effect is triggered by the explosion.                  |
| `damage_mortals`          | `0`     | The explosion does not damage mortals.                                      |
| `physics_explosion_power.max` | `0`     | No physics-based explosion power.                                           |
| `physics_throw_enabled`   | `0`     | No physics-based throwing effect.                                           |
| `sparks_enabled`          | `0`     | No sparks are generated.                                                    |
| `stains_enabled`          | `0`     | No stains are left behind.                                                  |

### ParticleEmitterComponent

This component is responsible for generating the actual visual particles that form the "poof."

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_green` | The material used for the emitted particles.                                |
| `gravity.y`               | `100.0` | The vertical gravity applied to the particles.                              |
| `lifetime_min`, `lifetime_max` | `0.5` - `1.5` | Particles live between 0.5 and 1.5 seconds.                                 |
| `count_min`, `count_max`  | `55` - `85` | The number of particles emitted per emission cycle.                         |
| `render_on_grid`          | `1`     | Particles are rendered on the game grid.                                    |
| `fade_based_on_lifetime`  | `1`     | Particles fade out as their lifetime decreases.                             |
| `area_circle_radius.max`  | `16`    | Particles are emitted within a circular area with a maximum radius of 16.   |
| `cosmetic_force_create`   | `1`     | Forces the creation of cosmetic particles.                                  |
| `collide_with_grid`       | `1`     | Particles can collide with the game grid.                                   |
| `airflow_force`           | `0.5`   | The strength of airflow affecting particles.                                |
| `airflow_time`            | `1.9`   | The duration airflow affects particles.                                     |
| `airflow_scale`           | `0.15`  | The scaling factor for airflow.                                             |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `1` | Particles are emitted every frame.                                          |
| `emit_cosmetic_particles` | `1`     | Ensures cosmetic particles are emitted.                                     |
| `x_vel_min`, `x_vel_max`  | `-120` - `120` | The range of horizontal velocity for emitted particles.                     |
| `y_vel_min`, `y_vel_max`  | `-180` - `40`  | The range of vertical velocity for emitted particles.                       |
| `is_emitting`             | `1`     | The particle emitter is active.                                             |