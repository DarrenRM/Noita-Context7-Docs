---
title: Perk Reroll Particle Effect
category: entities
---

---

# Perk Reroll Particle Effect

This entity defines the visual particle effects associated with the perk reroll mechanic in Noita. It primarily uses `ParticleEmitterComponent` to generate green sparks.

## Key Components

### ProjectileComponent

This component defines the projectile-like behavior of the entity. In this case, it's configured to exist for a short duration and then disappear without causing explosions or damage.

| Attribute             | Value | Description                                                                 |
| :-------------------- | :---- | :-------------------------------------------------------------------------- |
| `_enabled`            | `1`   | Enables the component.                                                      |
| `speed_min`, `speed_max` | `0`   | The projectile has no initial speed.                                        |
| `die_on_low_velocity` | `0`   | Does not die when its velocity becomes low.                                 |
| `on_death_explode`    | `0`   | Does not explode when it dies.                                              |
| `on_lifetime_out_explode` | `1`   | Explodes when its lifetime runs out (though the explosion is configured to do nothing). |
| `on_collision_die`    | `0`   | Does not die upon collision.                                                |
| `damage`              | `0`   | Deals no damage.                                                            |
| `lifetime`            | `2`   | The entity exists for 2 seconds.                                            |

#### config_explosion

This nested configuration defines the parameters for the explosion that occurs when the projectile's lifetime ends. All values are set to `0` or empty, indicating no actual visual or physical effect.

### ParticleEmitterComponent (Cosmetic Sparks)

This component is responsible for emitting cosmetic green sparks that create the visual flair of the reroll effect.

| Attribute                 | Value   | Description                                                                                             |
| :------------------------ | :------ | :------------------------------------------------------------------------------------------------------ |
| `emitted_material_name`   | `spark_green` | The material used for the emitted particles.                                                            |
| `gravity.y`               | `0.0`   | Particles are not affected by gravity.                                                                  |
| `lifetime_min`, `lifetime_max` | `1.5` - `2.5` | The duration each spark particle exists.                                                                |
| `count_min`, `count_max`  | `55` - `85` | The number of particles emitted per emission interval.                                                  |
| `render_on_grid`          | `1`     | Particles are rendered on the game grid.                                                                |
| `fade_based_on_lifetime`  | `1`     | Particles fade out as their lifetime decreases.                                                         |
| `area_circle_radius.max`  | `8`     | The maximum radius of the circular area from which particles are emitted.                               |
| `cosmetic_force_create`   | `0`     | Not used for forcing cosmetic particle creation.                                                        |
| `airflow_force`, `airflow_time`, `airflow_scale` | `0.5`, `1.9`, `0.15` | These parameters influence how particles are affected by airflow, giving them a slight drift. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `1` | Particles are emitted every frame.                                                                      |
| `emit_cosmetic_particles` | `1`     | This emitter is specifically for cosmetic particles.                                                    |
| `x_vel_min`, `x_vel_max`  | `-40` - `40` | The range of horizontal velocity applied to emitted particles.                                          |
| `y_vel_min`, `y_vel_max`  | `-40` - `40` | The range of vertical velocity applied to emitted particles.                                            |
| `is_emitting`             | `1`     | The emitter is active.                                                                                  |

### ParticleEmitterComponent (Real Particles - Minimal)

This second `ParticleEmitterComponent` also emits green sparks but is configured to create a smaller number of "real" particles, likely for a subtle visual cue.

| Attribute                 | Value   | Description                                                                                             |
| :------------------------ | :------ | :------------------------------------------------------------------------------------------------------ |
| `emitted_material_name`   | `spark_green` | The material used for the emitted particles.                                                            |
| `gravity.y`               | `0.0`   | Particles are not affected by gravity.                                                                  |
| `count_min`, `count_max`  | `15` - `25` | The number of particles emitted per emission interval.                                                  |
| `lifetime_min`, `lifetime_max` | `100` - `150` | The duration each spark particle exists (much longer than the cosmetic sparks).                         |
| `area_circle_radius.max`  | `10`    | The maximum radius of the circular area from which particles are emitted.                               |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `1` | Particles are emitted every frame.                                                                      |
| `create_real_particles`   | `1`     | This emitter is configured to create "real" particles, which might have slightly different behavior.    |
| `emit_real_particles`     | `1`     | Explicitly enables the emission of real particles.                                                      |
| `emit_cosmetic_particles` | `0`     | This emitter does not produce cosmetic particles.                                                       |
| `is_emitting`             | `1`     | The emitter is active.                                                                                  |