---
title: Pink Crystal Rocket Projectile
category: entities
---

# Pink Crystal Rocket Projectile

This document details the configuration for the "Pink Crystal Rocket" projectile in Noita, focusing on key attributes relevant for AI-assisted modding.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior of the rocket.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`      | 0.8, 1.0 | Controls the minimum and maximum lobbing angle, influencing trajectory.     |
| `speed_min`, `speed_max`  | 70, 70  | Sets the projectile's constant speed.                                       |
| `on_death_explode`        | 1       | The projectile explodes upon death (e.g., collision or lifetime end).       |
| `on_lifetime_out_explode` | 1       | The projectile explodes when its lifetime expires.                          |
| `on_collision_die`        | 1       | The projectile is destroyed upon collision with an entity.                  |
| `lifetime`                | 160     | The base duration in frames before the projectile expires.                  |
| `lifetime_randomness`     | 80      | Adds random variation to the projectile's lifetime.                         |
| `damage`                  | 2       | Base damage dealt by the projectile.                                        |
| `knockback_force`         | 4.0     | The force applied to entities upon impact.                                  |
| `camera_shake_when_shot`  | 15.0    | The intensity of camera shake when this projectile is fired.                |
| `muzzle_flash_file`       | `...muzzle_flash_magic_launcher.xml` | Specifies the particle effect for the muzzle flash. |
| `shoot_light_flash_r/g/b` | 215, 40, 255 | RGB values for the light flash when the projectile is shot.             |
| `shoot_light_flash_radius`| 90      | Radius of the light flash.                                                  |

### Explosion Configuration

The `config_explosion` sub-element within `ProjectileComponent` details the explosion's properties.

| Attribute                   | Value                               | Description                                                                 |
| :-------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `camera_shake`              | 90                                  | Intensity of camera shake during the explosion.                             |
| `explosion_radius`          | 20                                  | The radius of the explosion's effect.                                       |
| `explosion_sprite`          | `...explosion_032_pink.xml`         | The sprite used for the main explosion graphic.                             |
| `load_this_entity`          | `...main_swirly_pink.xml`           | The entity to load for more complex explosion effects.                      |
| `create_cell_probability`   | 40                                  | Chance (in %) to create cell-like destruction effects.                      |
| `hole_enabled`              | 1                                   | Enables the creation of holes in terrain.                                   |
| `ray_energy`                | 6200000                             | Energy value for raycasting effects during the explosion.                   |
| `damage`                    | 2.1                                 | Damage dealt by the explosion itself.                                       |
| `physics_explosion_power.min/max` | 1.0, 1.4                            | Minimum and maximum power for physics-based explosion forces.               |
| `sparks_enabled`            | 1                                   | Enables the emission of sparks.                                             |
| `spark_material`            | `plasma_fading_pink`                | The material used for the sparks.                                           |
| `stains_enabled`            | 1                                   | Enables the creation of impact stains.                                      |
| `audio_event_name`          | `explosions/magic_rocket_mid`       | The audio event triggered by the explosion.                                 |

## Movement and Targeting

### Velocity Component

The `VelocityComponent` governs the projectile's physical movement.

| Attribute     | Value   | Description                               |
| :------------ | :------ | :---------------------------------------- |
| `gravity_y`   | 50      | Downward acceleration due to gravity.     |
| `air_friction`| -2.0    | Resistance to movement in the air.        |
| `mass`        | 0.05    | The mass of the projectile.               |

### Homing Component

The `HomingComponent` allows the projectile to track targets.

| Attribute         | Value   | Description                                       |
| :---------------- | :------ | :------------------------------------------------ |
| `target_tag`      | `mortal`| The tag of entities to target.                    |
| `detect_distance` | 200     | The range within which targets can be detected.   |
| `max_turn_rate`   | 0.01    | The maximum rate at which the projectile can turn.|

## Visual and Audio Effects

### Sprite Component

The `SpriteComponent` defines the visual appearance of the projectile.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `image_file`| `data/projectiles_gfx/fireball_small.xml` | The sprite sheet or animation file.       |

### Light Component

The `LightComponent` adds a light source to the projectile.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `r`, `g`, `b` | 100, 10, 255 | RGB color values for the light.           |
| `radius`  | 150   | The radius of the light's illumination.   |

### Particle Emitters

Multiple `ParticleEmitterComponent` instances are used to create various visual effects, such as smoke trails, sparks, and cosmetic particles.

*   **Smoke Emitter:** Emits `smoke` particles with low velocity and short lifetime.
*   **Plasma Trail Emitters (Multiple):** Emit `plasma_fading_pink` particles with varying gravity, lifetime, and airflow to create a dynamic trail effect. Some are configured for cosmetic particles (`emit_cosmetic_particles="1"`).
*   **Sparse Emitter:** Emits `plasma_fading_pink` particles with a longer lifetime and a specific emission interval, creating a less dense, more spread-out effect.
*   **Trailing Emitter:** Emits `plasma_fading_pink` particles with a significant gravity and lifetime, contributing to the overall visual trail.

### Audio Component

The `AudioComponent` specifies the sound effects associated with the projectile.

| Attribute      | Value                       | Description                               |
| :------------- | :-------------------------- | :---------------------------------------- |
| `file`         | `data/audio/Desktop/projectiles.bank` | The audio bank containing the sound events. |
| `event_root`   | `player_projectiles/bullet_rocket` | The root event name for projectile sounds. |

## Variable Storage

The `VariableStorageComponent` can be used to store custom variables.

| Attribute | Value                                       | Description                               |
| :-------- | :------------------------------------------ | :---------------------------------------- |
| `name`    | `projectile_file`                           | The name of the variable.                 |
| `value_string`| `data/entities/projectiles/crystal_pink_projectile.xml` | The string value assigned to the variable. |