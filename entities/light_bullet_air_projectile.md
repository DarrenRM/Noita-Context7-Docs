---
title: Light Bullet (Air) Projectile
category: entities
---

# Light Bullet (Air) Projectile

This document details the configuration for the "Light Bullet (Air)" projectile in Noita, focusing on attributes relevant for AI-assisted modding.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior and characteristics of the projectile.

### Key Attributes:

| Attribute             | Value   | Description                                                                 |
| :-------------------- | :------ | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`  | 0.5-0.7 | Controls the arc/lob of the projectile.                                     |
| `speed_min`, `speed_max`| 350-450 | Defines the initial velocity range of the projectile.                       |
| `friction`            | 1       | How much the projectile's velocity is reduced over time.                    |
| `lifetime`            | 40      | Duration in frames before the projectile expires.                           |
| `damage`              | 0.23    | The base damage dealt by the projectile.                                    |
| `lifetime_randomness` | 7       | Adds variability to the projectile's lifetime.                              |
| `knockback_force`     | 100.0   | The force applied to entities upon impact.                                  |
| `muzzle_flash_file`   | `data/entities/particles/muzzle_flashes/muzzle_flash_air.xml` | Specifies the particle effect for the muzzle flash. |
| `shoot_light_flash_r`, `g`, `b`, `radius` | 128, 128, 128, 48 | Defines the color and radius of the light flash when shot. |

### Collision and Death Behavior:

| Attribute             | Value | Description                                                                 |
| :-------------------- | :---- | :-------------------------------------------------------------------------- |
| `on_collision_die`    | 1     | The projectile is destroyed upon colliding with an entity.                  |
| `explosion_dont_damage_shooter` | 1 | The projectile's death explosion (if any) does not damage the shooter. |

### Explosion Configuration (`config_explosion`):

This projectile's explosion is configured to have no damage or physical impact.

| Attribute             | Value | Description                                                                 |
| :-------------------- | :---- | :-------------------------------------------------------------------------- |
| `damage`              | 0.0   | No damage is dealt by the explosion.                                        |
| `camera_shake`        | 0.0   | No camera shake is triggered by the explosion.                              |
| `explosion_radius`    | 0     | The explosion has no radius.                                                |
| `ray_energy`          | 0     | No energy is transferred via rays from the explosion.                       |
| `physics_throw_enabled` | 0 | No physics-based throwing of objects occurs.                                |

## Visual and Particle Effects

### Sprite Component:

| Attribute     | Value                               | Description                                                                 |
| :------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`  | `data/particles/dummy.xml`          | Uses a dummy sprite, suggesting visual effects are handled by particles.    |
| `alpha`       | 1                                   | Fully opaque.                                                               |

### Particle Emitters:

This projectile utilizes two `ParticleEmitterComponent`s to generate visual effects.

#### Emitter 1 (Trail/Impact Sparks):

| Attribute               | Value   | Description                                                                 |
| :---------------------- | :------ | :-------------------------------------------------------------------------- |
| `emitted_material_name` | `spark_white` | The type of particle emitted.                                               |
| `x_vel_min`, `max`      | 0-40    | Horizontal velocity range for emitted particles.                            |
| `y_vel_min`, `max`      | -10-10  | Vertical velocity range for emitted particles.                              |
| `gravity.y`             | 0.0     | Particles are not affected by gravity.                                      |
| `count_min`, `max`      | 3-4     | Number of particles emitted per emission.                                   |
| `lifetime_min`, `max`   | 0.2-1.2 | Duration in seconds for emitted particles.                                  |
| `airflow_force`         | 1.5     | Strength of airflow affecting particles.                                    |
| `airflow_time`          | 1.101   | Duration in seconds airflow affects particles.                              |
| `emission_interval_min_frames`, `max_frames` | 1-1 | Particles are emitted continuously. |

#### Emitter 2 (Lingering Sparks):

| Attribute               | Value   | Description                                                                 |
| :---------------------- | :------ | :-------------------------------------------------------------------------- |
| `emitted_material_name` | `spark_white` | The type of particle emitted.                                               |
| `x_vel_min`, `max`      | 0-0     | No horizontal velocity for these particles.                                 |
| `y_vel_min`, `max`      | -10-10  | Vertical velocity range for emitted particles.                              |
| `gravity.y`             | 0.0     | Particles are not affected by gravity.                                      |
| `count_min`, `max`      | 1-2     | Number of particles emitted per emission.                                   |
| `lifetime_min`, `max`   | 1.2-3.2 | Longer duration for these lingering particles.                              |
| `airflow_force`         | 0.5     | Weaker airflow affecting particles.                                         |
| `airflow_time`          | 3.101   | Longer duration airflow affects particles.                                  |

## Other Components

### Light Component:

| Attribute | Value | Description                                 |
| :-------- | :---- | :------------------------------------------ |
| `radius`  | 30    | The radius of the light emitted by the projectile. |

### Magic Convert Material Component:

This component is present but configured to not convert any materials.

| Attribute   | Value | Description                                                                 |
| :---------- | :---- | :-------------------------------------------------------------------------- |
| `from_material` | ""    | No material is targeted for conversion.                                     |
| `to_material`   | ""    | No material is converted into.                                              |
| `radius`    | 10    | The radius of the conversion effect (not active here).                      |

### Audio Component:

| Attribute     | Value                                       | Description                                                                 |
| :------------ | :------------------------------------------ | :-------------------------------------------------------------------------- |
| `file`        | `data/audio/Desktop/projectiles.bank`       | The audio bank containing the sound effects.                                |
| `event_root`  | `player_projectiles/bullet_burst_of_air`    | The specific sound event triggered by this projectile.                      |

### Variable Storage Component:

| Attribute   | Value                                       | Description                                                                 |
| :---------- | :------------------------------------------ | :-------------------------------------------------------------------------- |
| `name`      | `projectile_file`                         | The name of the variable.                                                   |
| `value_string` | `data/entities/projectiles/deck/light_bullet_air.xml` | Stores the path to this projectile's entity file. |