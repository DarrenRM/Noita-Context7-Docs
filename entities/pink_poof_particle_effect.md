---
title: Pink Poof Particle Effect
category: entities
---

# Pink Poof Particle Effect

This entity defines a particle effect that creates a "pink poof" visual. It's primarily used for cosmetic purposes, such as indicating a minor magical event or a small explosion.

## Key Components

### ProjectileComponent

This component defines the behavior of the entity as a projectile, though in this case, it's configured to not act like a typical projectile.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `_enabled`                | Whether the component is active. Set to `1` (enabled).                      |
| `speed_min`, `speed_max`  | Minimum and maximum speed. Set to `0`, indicating no movement as a projectile. |
| `die_on_low_velocity`     | If `0`, the projectile won't die due to low velocity.                       |
| `on_death_explode`        | If `0`, no explosion occurs upon death.                                     |
| `on_death_gfx_leave_sprite` | If `0`, no sprite is left behind upon death.                                |
| `on_lifetime_out_explode` | If `1`, an explosion occurs when the lifetime expires.                      |
| `on_collision_die`        | If `0`, the projectile does not die upon collision.                         |
| `damage`                  | Damage dealt by the projectile. Set to `0`.                                 |
| `lifetime`                | The duration in seconds before the projectile expires. Set to `5`.          |

#### `config_explosion` (within `ProjectileComponent`)

This sub-component defines the properties of the explosion that occurs when `on_lifetime_out_explode` is `1`.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `never_cache`             | If `1`, this explosion will not be cached.                                  |
| `damage`                  | Damage dealt by the explosion. Set to `0`.                                  |
| `camera_shake`            | Amount of camera shake. Set to `0`.                                         |
| `explosion_radius`        | Radius of the explosion. Set to `0`.                                        |
| `particle_effect`         | If `0`, no additional particle effects are created by the explosion.        |
| `damage_mortals`          | If `0`, the explosion does not damage living entities.                      |
| `physics_explosion_power.max` | Maximum physics force applied by the explosion. Set to `0`.                 |
| `sparks_enabled`          | If `0`, no sparks are generated.                                            |
| `stains_enabled`          | If `0`, no stains are left behind.                                          |

### ParticleEmitterComponent

This component is responsible for generating the actual visual particles that form the "pink poof".

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material used for the emitted particles. Set to `plasma_fading_pink`.   |
| `gravity.y`               | The gravitational pull on the particles in the Y-axis. Set to `100.0`.      |
| `lifetime_min`, `lifetime_max` | Minimum and maximum lifetime of individual particles in seconds. Set to `0.5` and `1.5`. |
| `count_min`, `count_max`  | Minimum and maximum number of particles emitted per emission cycle. Set to `55` and `85`. |
| `render_on_grid`          | If `1`, particles are rendered on the game grid.                            |
| `fade_based_on_lifetime`  | If `1`, particles fade out as their lifetime decreases.                     |
| `area_circle_radius.max`  | Maximum radius of the circular area from which particles are emitted. Set to `12`. |
| `cosmetic_force_create`   | If `0`, particles are not created with a cosmetic force.                    |
| `airflow_force`           | Strength of airflow affecting particles. Set to `0.5`.                      |
| `airflow_time`            | Duration airflow affects particles. Set to `1.9`.                           |
| `airflow_scale`           | Scale of airflow effect. Set to `0.15`.                                     |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Controls how often particles are emitted. Set to `1` frame for both, meaning continuous emission. |
| `emit_cosmetic_particles` | If `1`, particles are considered cosmetic.                                  |
| `x_vel_min`, `x_vel_max`  | Minimum and maximum velocity in the X-axis for emitted particles. Set to `-120` and `120`. |
| `y_vel_min`, `y_vel_max`  | Minimum and maximum velocity in the Y-axis for emitted particles. Set to `-180` and `40`. |
| `is_emitting`             | If `1`, the emitter is active.                                              |