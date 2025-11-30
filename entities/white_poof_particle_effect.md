---
title: White Poof Particle Effect
category: data/entities/particles
---

# White Poof Particle Effect

This entity defines a particle effect that creates a "white poof" visual. It's primarily used for cosmetic purposes, such as indicating a minor impact or disappearance.

## Key Components

### ProjectileComponent

This component controls the projectile-like behavior of the entity. In this case, it's configured to primarily manage the lifetime and trigger particle emission upon expiration.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `_enabled`                | `1`     | Enables the component.                                                      |
| `speed_min`, `speed_max`  | `0`     | The projectile has no initial velocity.                                     |
| `die_on_low_velocity`     | `0`     | Does not die when velocity becomes low.                                     |
| `on_death_explode`        | `0`     | Does not create an explosion when it dies.                                  |
| `on_death_gfx_leave_sprite` | `0`     | Does not leave a sprite graphic when it dies.                               |
| `on_lifetime_out_explode` | `1`     | Triggers an explosion-like effect (particle emission) when lifetime ends. |
| `on_collision_die`        | `0`     | Does not die upon collision.                                                |
| `damage`                  | `0`     | Deals no damage.                                                            |
| `lifetime`                | `5`     | The entity exists for 5 seconds before its lifetime expires.                |

#### `config_explosion`

This nested configuration defines the parameters for the "explosion" that occurs when the `ProjectileComponent`'s lifetime ends. For this particle effect, most explosion properties are disabled.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `never_cache`             | `1`     | Prevents caching of this explosion configuration.                             |
| `damage`                  | `0`     | Deals no damage.                                                            |
| `camera_shake`            | `0`     | No camera shake is applied.                                                 |
| `explosion_radius`        | `0`     | No explosion radius.                                                        |
| `explosion_sprite`        | `""`    | No explosion sprite is used.                                                |
| `explosion_sprite_lifetime` | `0`     | No sprite lifetime.                                                         |
| `create_cell_material`    | `""`    | No material cells are created.                                              |
| `create_cell_probability` | `0`     | No probability of creating material cells.                                  |
| `hole_destroy_liquid`     | `0`     | Does not destroy liquids.                                                   |
| `hole_enabled`            | `0`     | No holes are created.                                                       |
| `particle_effect`         | `0`     | No additional particle effects are spawned by the explosion itself.         |
| `damage_mortals`          | `0`     | Does not damage mortals.                                                    |
| `physics_explosion_power.max` | `0`     | No physics-based explosion force.                                           |
| `physics_throw_enabled`   | `0`     | No physics-based throwing of objects.                                       |
| `shake_vegetation`        | `0`     | Does not shake vegetation.                                                  |
| `sparks_enabled`          | `0`     | No sparks are generated.                                                    |
| `stains_enabled`          | `0`     | No stains are created.                                                      |

### ParticleEmitterComponent

This component is responsible for generating the actual visual particles that form the "white poof."

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_white` | The material used for the emitted particles.                                |
| `gravity.y`               | `100.0` | Downward gravity applied to the particles.                                  |
| `lifetime_min`, `lifetime_max` | `0.5` - `1.5` | Particles live between 0.5 and 1.5 seconds.                                 |
| `count_min`, `count_max`  | `55` - `85` | The number of particles emitted per emission interval.                      |
| `render_on_grid`          | `1`     | Particles are rendered on the game grid.                                    |
| `fade_based_on_lifetime`  | `1`     | Particles fade out as their lifetime decreases.                             |
| `area_circle_radius.max`  | `12`    | Particles are emitted within a circle of up to 12 pixels radius.            |
| `cosmetic_force_create`   | `0`     | Particles are not forced to be cosmetic.                                    |
| `airflow_force`           | `0.5`   | A slight force applied by airflow.                                          |
| `airflow_time`            | `1.9`   | Duration of airflow influence.                                              |
| `airflow_scale`           | `0.15`  | Scale of the airflow effect.                                                |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `1` | Particles are emitted every frame.                                          |
| `emit_cosmetic_particles` | `1`     | Emits cosmetic particles.                                                   |
| `x_vel_min`, `x_vel_max`  | `-120` - `120` | Horizontal velocity range for emitted particles.                            |
| `y_vel_min`, `y_vel_max`  | `-180` - `40`  | Vertical velocity range for emitted particles (upward bias).                |
| `is_emitting`             | `1`     | The particle emitter is active.                                             |