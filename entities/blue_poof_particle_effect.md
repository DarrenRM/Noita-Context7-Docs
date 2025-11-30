---
title: Blue Poof Particle Effect
category: entities
---

# Blue Poof Particle Effect

This entity defines a visual particle effect that resembles a "blue poof" or puff of smoke. It's primarily used for cosmetic purposes and doesn't have significant gameplay impact.

## Key Components

### ProjectileComponent

This component defines the projectile-like behavior of the entity. In this case, it's configured to exist for a short duration and then trigger an explosion, which is used here to spawn the particles.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `_enabled`                | `1`     | Enables the component.                                                      |
| `speed_min`, `speed_max`  | `0`     | The projectile has no initial velocity.                                     |
| `die_on_low_velocity`     | `0`     | Does not die when its velocity becomes low.                                 |
| `on_death_explode`        | `0`     | Does not create an explosion when it dies naturally.                        |
| `on_lifetime_out_explode` | `1`     | Creates an explosion when its lifetime expires. This is how particles spawn. |
| `lifetime`                | `5`     | The entity exists for 5 seconds before its lifetime expires.                |

#### config_explosion

This sub-element configures the explosion that occurs when the `ProjectileComponent`'s lifetime runs out. For this particle effect, the explosion is designed to be purely visual and have no damaging or destructive properties.

| Attribute              | Value | Description                                                                 |
| :--------------------- | :---- | :-------------------------------------------------------------------------- |
| `damage`               | `0`   | The explosion deals no damage.                                              |
| `explosion_radius`     | `0`   | The explosion has no radius.                                                |
| `particle_effect`      | `0`   | No additional particle effects are spawned by the explosion itself.         |
| `damage_mortals`       | `0`   | The explosion does not damage living entities.                              |
| `physics_explosion_power.max` | `0` | The explosion has no physics impact.                                        |
| `sparks_enabled`       | `0`   | No sparks are generated.                                                    |
| `stains_enabled`       | `0`   | No stains are left behind.                                                  |

### ParticleEmitterComponent

This component is responsible for generating the actual visual particles that make up the "blue poof" effect.

| Attribute                 | Value   | Description                                                                                             |
| :------------------------ | :------ | :------------------------------------------------------------------------------------------------------ |
| `emitted_material_name`   | `plasma_fading` | The material used for the emitted particles.                                                            |
| `gravity.y`               | `100.0` | The particles are affected by gravity, pulling them downwards.                                          |
| `lifetime_min`, `lifetime_max` | `0.5` - `1.5` | Each particle lives for a duration between 0.5 and 1.5 seconds.                                           |
| `count_min`, `count_max`  | `55` - `85` | The number of particles emitted each time the emitter activates.                                        |
| `render_on_grid`          | `1`     | Particles are rendered on the game grid.                                                                |
| `fade_based_on_lifetime`  | `1`     | Particles fade out as their lifetime decreases.                                                         |
| `area_circle_radius.max`  | `12`    | Particles are emitted within a circular area with a maximum radius of 12 units.                         |
| `airflow_force`, `airflow_time`, `airflow_scale` | `0.5`, `1.9`, `0.15` | These attributes control how particles are affected by airflow, creating a swirling or drifting effect. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `1` | Particles are emitted continuously with no delay between emissions.                                       |
| `emit_cosmetic_particles` | `1`     | Ensures these are treated as cosmetic particles, not affecting gameplay directly.                       |
| `x_vel_min`, `x_vel_max`  | `-120` - `120` | Particles are emitted with horizontal velocities ranging from -120 to 120.                              |
| `y_vel_min`, `y_vel_max`  | `-180` - `40`  | Particles are emitted with vertical velocities ranging from -180 (upwards) to 40 (downwards).           |
| `is_emitting`             | `1`     | The particle emitter is active.                                                                         |