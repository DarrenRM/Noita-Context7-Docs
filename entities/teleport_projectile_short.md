---
title: Teleport Projectile (Short)
category: entities
---

---

# Teleport Projectile (Short)

This document details the configuration for the "teleport_projectile_short.xml" entity in Noita, focusing on its properties as a player projectile with teleportation capabilities.

## Core Components

### ProjectileComponent
This is the primary component defining the projectile's behavior.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `_enabled`                | `1`          | Enables the component.                                                      |
| `lob_min`, `lob_max`      | `0.5`, `0.7` | Controls the arc of the projectile.                                         |
| `speed_min`, `speed_max`  | `1350`       | Sets the projectile's speed.                                                |
| `friction`                | `1`          | How much the projectile slows down over time.                               |
| `direction_random_rad`    | `0.00`       | Random deviation in projectile direction (0 means no deviation).            |
| `on_death_explode`        | `1`          | Triggers an explosion when the projectile dies.                             |
| `on_death_gfx_leave_sprite` | `0`          | Whether to leave a sprite graphic when it dies.                             |
| `on_lifetime_out_explode` | `1`          | Triggers an explosion when the projectile's lifetime expires.               |
| `explosion_dont_damage_shooter` | `1`          | Prevents the projectile's explosion from damaging the player who shot it. |
| `on_collision_die`        | `1`          | The projectile dies upon collision.                                         |
| `on_collision_remove_projectile` | `0`          | Does not remove the projectile entity upon collision (it dies instead).     |
| `lifetime`                | `8`          | The duration in seconds before the projectile expires.                      |
| `damage`                  | `0.0`        | The damage dealt by the projectile.                                         |
| `shoot_light_flash_radius`| `120`        | Radius of the light flash when the projectile is shot.                      |
| `shoot_light_flash_r/g/b` | `140/210/255`| Color of the light flash.                                                   |

#### `config_explosion`
Defines the properties of the explosion triggered by the projectile.

| Attribute              | Value   | Description                                                               |
| :--------------------- | :------ | :------------------------------------------------------------------------ |
| `damage`               | `0.0`   | Damage dealt by the explosion.                                            |
| `camera_shake`         | `0.5`   | Intensity of camera shake caused by the explosion.                        |
| `explosion_radius`     | `2`     | The radius of the explosion.                                              |
| `explosion_sprite`     | `...`   | Path to the sprite used for the explosion effect.                         |
| `hole_enabled`         | `1`     | Enables the creation of holes in terrain.                                 |
| `ray_energy`           | `40000` | Energy of the explosion's rays, affecting terrain destruction.            |
| `damage_mortals`       | `1`     | Whether the explosion damages living entities.                            |
| `physics_explosion_power.min/max` | `0` | Minimum and maximum force of physics-based explosions.                    |
| `shake_vegetation`     | `1`     | Whether the explosion shakes vegetation.                                  |
| `stains_enabled`       | `1`     | Enables the creation of impact stains.                                    |
| `stains_radius`        | `3`     | Radius of the impact stains.                                              |

### TeleportProjectileComponent
Specific component for teleportation projectiles.

| Attribute              | Value   | Description                                                               |
| :--------------------- | :------ | :------------------------------------------------------------------------ |
| `min_distance_from_wall` | `4`     | Minimum distance the projectile must be from a wall to teleport.          |

### Base Component
Inherits base projectile properties.

#### `VelocityComponent`
Defines the projectile's physics properties.

| Attribute     | Value | Description                               |
| :------------ | :---- | :---------------------------------------- |
| `gravity_y`   | `200` | Downward acceleration due to gravity.     |
| `air_friction`| `1.7` | Resistance from air.                      |
| `mass`        | `0.04`| The mass of the projectile.               |

### SpriteComponent
Defines the visual representation of the projectile.
- `image_file`: Empty, suggesting it might rely on particle effects or other visual components.

### AudioComponent
Handles sound effects for the projectile.
- `file`: `data/audio/Desktop/projectiles.bank`
- `event_root`: `player_projectiles/teleport`

## Particle Emitters

The projectile utilizes several `ParticleEmitterComponent` and `SpriteParticleEmitterComponent` to create visual effects.

### Trail Emitter 1
Creates a continuous trail effect.

| Attribute              | Value   | Description                                                               |
| :--------------------- | :------ | :------------------------------------------------------------------------ |
| `emitted_material_name`| `spark_blue` | The material used for the emitted particles.                              |
| `gravity.y`            | `0.0`   | No gravity applied to these particles.                                    |
| `count_min/max`        | `1`/`2` | Number of particles emitted per interval.                                 |
| `x/y_pos_offset_min/max`| `-1` to `1` | Random offset from the projectile's center.                               |
| `x/y_vel_min/max`      | `0` to `5` | Velocity of emitted particles.                                            |
| `is_trail`             | `1`     | Indicates this is a trail emitter.                                        |
| `trail_gap`            | `1.5`   | Spacing between trail particles.                                          |
| `lifetime_min/max`     | `0.4`/`1.8` | Duration of each particle.                                                |
| `airflow_force`        | `4.1`   | Force applied by airflow.                                                 |
| `airflow_time`         | `0.101` | Duration airflow affects particles.                                       |
| `airflow_scale`        | `10.01` | Scale of airflow effect.                                                  |
| `emit_real_particles`  | `0`     | Emits cosmetic particles, not physics-simulated ones.                     |
| `render_on_grid`       | `1`     | Particles are rendered on the game grid.                                  |
| `fade_based_on_lifetime`| `1`     | Particles fade out as their lifetime decreases.                           |
| `emit_cosmetic_particles`| `1`     | Explicitly emits cosmetic particles.                                      |
| `emission_interval_min/max_frames` | `1`/`2` | How often particles are emitted (in frames).                              |
| `is_emitting`          | `1`     | The emitter is active.                                                    |

### Burst Emitter 2
Creates a burst of particles upon emission or death.

| Attribute              | Value   | Description                                                               |
| :--------------------- | :------ | :------------------------------------------------------------------------ |
| `emitted_material_name`| `spark_blue` | The material used for the emitted particles.                              |
| `gravity.y`            | `0.0`   | No gravity applied to these particles.                                    |
| `count_min/max`        | `70`/`140` | Number of particles emitted in a burst.                                   |
| `x/y_pos_offset_min/max`| `-2` to `2` | Random offset from the projectile's center.                               |
| `x/y_vel_min/max`      | `-10` to `10` | Velocity of emitted particles.                                            |
| `is_trail`             | `1`     | Indicates this is a trail emitter (though used for bursts here).          |
| `trail_gap`            | `1.5`   | Spacing between trail particles.                                          |
| `lifetime_min/max`     | `0.4`/`0.6` | Duration of each particle.                                                |
| `airflow_force`        | `0.1`   | Force applied by airflow.                                                 |
| `airflow_time`         | `0.101` | Duration airflow affects particles.                                       |
| `airflow_scale`        | `2.01`  | Scale of airflow effect.                                                  |
| `emit_real_particles`  | `0`     | Emits cosmetic particles.                                                 |
| `fade_based_on_lifetime`| `1`     | Particles fade out as their lifetime decreases.                           |
| `render_on_grid`       | `1`     | Particles are rendered on the game grid.                                  |
| `emit_cosmetic_particles`| `1`     | Explicitly emits cosmetic particles.                                      |
| `emission_interval_min/max_frames` | `1`/`1` | How often particles are emitted (in frames).                              |
| `is_emitting`          | `1`     | The emitter is active.                                                    |

### Sprite Particle Emitter
Emits sprite-based particles for additional visual flair.

| Attribute              | Value        | Description                                                               |
| :--------------------- | :----------- | :------------------------------------------------------------------------ |
| `sprite_file`          | `...shine_02.xml` | Path to the sprite used for these particles.                              |
| `lifetime`             | `2`          | Duration of each sprite particle.                                         |
| `color.r/g/b/a`        | `1/1/1/1`    | Initial color of the particles.                                           |
| `color_change.a`       | `-1`         | Alpha value decreases over time.                                          |
| `gravity.y`            | `10`         | Downward acceleration for these particles.                                |
| `velocity_slowdown`    | `0.5`        | How quickly particles lose velocity.                                      |
| `emission_interval_min/max_frames` | `2`/`4` | How often particles are emitted.                                          |
| `count_min/max`        | `1`/`2`      | Number of particles emitted per interval.                                 |
| `randomize_rotation`   | `-3.14` to `3.14` | Random initial rotation.                                                  |
| `randomize_angular_velocity` | `-1` to `1` | Random initial angular velocity.                                          |
| `randomize_position.min/max_x/y` | `-2` to `2` | Random offset from the projectile's center.                               |
| `randomize_velocity.min/max_x/y` | `-2` to `10` | Random initial velocity.                                                  |

## Variable Storage

### VariableStorageComponent
Stores variables that can be accessed by other components or scripts.

| Attribute   | Value                                       | Description                                                               |
| :---------- | :------------------------------------------ | :------------------------------------------------------------------------ |
| `name`      | `projectile_file`                           | The name of the variable.                                                 |
| `value_string`| `data/entities/projectiles/deck/teleport_projectile_short.xml` | The string value stored, likely referencing its own file path.            |