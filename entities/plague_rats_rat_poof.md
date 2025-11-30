---
title: Plague Rats Rat Poof
category: entities
---

# Plague Rats Rat Poof

This entity defines the visual effect that occurs when the "Plague Rats" perk triggers a rat to disappear. It primarily uses particle emitters to create a poofing animation.

## Key Components

### ProjectileComponent

This component defines the projectile-like behavior of the poof effect.

| Attribute             | Value | Description                                                                 |
| :-------------------- | :---- | :-------------------------------------------------------------------------- |
| `_enabled`            | `1`   | Enables the component.                                                      |
| `speed_min`, `speed_max` | `0`   | The poof effect does not move.                                              |
| `die_on_low_velocity` | `0`   | The effect does not die if its velocity becomes low.                        |
| `on_death_explode`    | `0`   | The effect does not explode upon death.                                     |
| `on_lifetime_out_explode` | `1`   | The effect will "explode" (trigger its particle emitters) when its lifetime ends. |
| `on_collision_die`    | `0`   | The effect does not die upon collision.                                     |
| `damage`              | `0`   | The effect deals no damage.                                                 |
| `lifetime`            | `2`   | The effect lasts for 2 seconds.                                             |

#### config_explosion

This sub-component details the explosion properties, which are largely disabled for this effect.

| Attribute             | Value | Description                                                                 |
| :-------------------- | :---- | :-------------------------------------------------------------------------- |
| `damage`              | `0`   | No damage is dealt by the "explosion".                                      |
| `explosion_radius`    | `0`   | No explosion radius.                                                        |
| `create_cell_material`| `""`  | No material is created.                                                     |
| `particle_effect`     | `0`   | No specific particle effect is triggered by the "explosion".                |
| `damage_mortals`      | `0`   | No damage to mortals.                                                       |
| `physics_explosion_power.max` | `0` | No physics-based explosion force.                                           |

### ParticleEmitterComponent (Primary Poof)

This component is responsible for the main visual poof of purple sparks.

| Attribute                 | Value | Description                                                                 |
| :------------------------ | :---- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_purple_bright` | The material used for the emitted particles.                                |
| `gravity.y`               | `0.0` | Particles are not affected by gravity.                                      |
| `lifetime_min`, `lifetime_max` | `1.5` - `2.5` | Particles last between 1.5 and 2.5 seconds.                                 |
| `count_min`, `count_max`  | `55` - `85` | Emits between 55 and 85 particles.                                          |
| `render_on_grid`          | `1`   | Particles are rendered on the game grid.                                    |
| `fade_based_on_lifetime`  | `1`   | Particles fade out as their lifetime decreases.                             |
| `area_circle_radius.max`  | `8`   | Particles are emitted within a circle of up to 8 radius.                    |
| `cosmetic_force_create`   | `0`   | Particles are not forced to be cosmetic.                                    |
| `airflow_force`           | `0.5` | A slight airflow force is applied.                                          |
| `airflow_time`            | `1.9` | Airflow lasts for 1.9 seconds.                                              |
| `airflow_scale`           | `0.15`| The scale of the airflow effect.                                            |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `1` | Particles are emitted continuously.                                         |
| `emit_cosmetic_particles` | `1`   | Cosmetic particles are emitted.                                             |
| `x_vel_min`, `x_vel_max`  | `-40` - `40` | Particles have horizontal velocity.                                         |
| `y_vel_min`, `y_vel_max`  | `-40` - `40` | Particles have vertical velocity.                                           |
| `is_emitting`             | `1`   | The emitter is active.                                                      |

### ParticleEmitterComponent (Secondary, Longer-lasting)

This component emits a smaller number of longer-lasting particles, likely for a lingering visual effect.

| Attribute                 | Value | Description                                                                 |
| :------------------------ | :---- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_purple_bright` | The material used for the emitted particles.                                |
| `gravity.y`               | `0.0` | Particles are not affected by gravity.                                      |
| `count_min`, `count_max`  | `15` - `25` | Emits between 15 and 25 particles.                                          |
| `lifetime_min`, `lifetime_max` | `100` - `150` | Particles last between 100 and 150 frames (approximately 4-6 seconds).      |
| `area_circle_radius.max`  | `10`  | Particles are emitted within a circle of up to 10 radius.                   |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `1` | Particles are emitted continuously.                                         |
| `create_real_particles`   | `1`   | Real particles are created.                                                 |
| `emit_real_particles`     | `1`   | Real particles are emitted.                                                 |
| `emit_cosmetic_particles` | `0`   | Cosmetic particles are not emitted by this emitter.                         |
| `is_emitting`             | `1`   | The emitter is active.                                                      |