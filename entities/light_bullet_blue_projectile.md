---
title: Light Bullet (Blue) Projectile
category: entities
---

# Light Bullet (Blue) Projectile

This document details the configuration for the "Light Bullet (Blue)" projectile in Noita, focusing on attributes relevant to AI-assisted modding.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior and characteristics of the projectile.

| Attribute | Value | Description |
|---|---|---|
| `speed_min` | `650` | Minimum initial velocity of the projectile. |
| `speed_max` | `750` | Maximum initial velocity of the projectile. |
| `lifetime` | `40` | Duration in frames before the projectile expires. |
| `lifetime_randomness` | `7` | Adds random variation to the projectile's lifetime. |
| `damage` | `0.15` | Base damage dealt by the projectile. |
| `on_death_explode` | `1` | Triggers an explosion upon the projectile's death. |
| `on_lifetime_out_explode` | `1` | Triggers an explosion when the projectile's lifetime expires. |
| `on_collision_die` | `1` | The projectile dies upon colliding with something. |
| `explosion_dont_damage_shooter` | `1` | The explosion caused by this projectile does not harm the entity that fired it. |
| `shoot_light_flash_r`, `g`, `b` | `125`, `140`, `255` | RGB values for the light flash emitted when the projectile is fired. |
| `shoot_light_flash_radius` | `64` | Radius of the light flash emitted when fired. |

## Visuals

The `SpriteComponent` handles the visual representation of the projectile.

| Attribute | Value | Description |
|---|---|---|
| `image_file` | `data/projectiles_gfx/spark_blue.xml` | Path to the sprite sheet used for the projectile. |
| `additive` | `1` | Enables additive blending for the sprite, often used for glowing effects. |

## Particle Emitters

This projectile utilizes multiple `ParticleEmitterComponent`s to generate visual effects.

### Dense Emitter

This emitter creates a continuous trail of particles.

| Attribute | Value | Description |
|---|---|---|
| `emitted_material_name` | `plasma_fading` | The material of the particles to be emitted. |
| `count_min`, `count_max` | `4`, `10` | Number of particles emitted per emission. |
| `lifetime_min`, `lifetime_max` | `0.8`, `0.9` | Duration of emitted particles. |
| `is_trail` | `1` | Indicates this emitter is intended for trail effects. |
| `airflow_force` | `10.5` | Force applied by airflow to the particles. |

### Sparse Emitter

This emitter creates less frequent, more dispersed particles.

| Attribute | Value | Description |
|---|---|---|
| `emitted_material_name` | `plasma_fading` | The material of the particles to be emitted. |
| `x_vel_min`, `x_vel_max` | `20`, `40` | Horizontal velocity range for emitted particles. |
| `count_min`, `count_max` | `1`, `2` | Number of particles emitted per emission. |
| `lifetime_min`, `lifetime_max` | `0.6`, `0.8` | Duration of emitted particles. |
| `emission_interval_min_frames`, `max_frames` | `1`, `10` | Controls the frequency of particle emissions. |

### Very Sparse Emitter

This emitter produces very infrequent, long-lasting particles.

| Attribute | Value | Description |
|---|---|---|
| `emitted_material_name` | `plasma_fading` | The material of the particles to be emitted. |
| `x_vel_min`, `x_vel_max` | `10`, `20` | Horizontal velocity range for emitted particles. |
| `count_min`, `count_max` | `1`, `1` | Number of particles emitted per emission. |
| `lifetime_min`, `lifetime_max` | `1.4`, `1.5` | Duration of emitted particles. |
| `emission_interval_min_frames`, `max_frames` | `10`, `20` | Controls the frequency of particle emissions. |

## Explosion Configuration

The `config_explosion` element within `ProjectileComponent` defines the properties of the explosion triggered by the projectile.

| Attribute | Value | Description |
|---|---|---|
| `damage` | `0.1` | Damage dealt by the explosion. |
| `camera_shake` | `0.5` | Intensity of camera shake caused by the explosion. |
| `explosion_radius` | `12` | The radius of the explosion's effect. |
| `explosion_sprite` | `data/particles/explosion_016_plasma.xml` | Sprite used for the explosion visual. |
| `hole_enabled` | `1` | Enables the creation of holes in terrain by the explosion. |
| `ray_energy` | `500000` | Energy value for raycasting effects of the explosion. |
| `max_durability_to_destroy` | `9` | Maximum durability of objects that can be destroyed by the explosion. |
| `physics_explosion_power.max` | `0.3` | Maximum force applied to physics objects by the explosion. |
| `stains_enabled` | `1` | Enables the creation of impact stains. |
| `stains_radius` | `3` | Radius of the impact stains. |

## Lighting

The `LightComponent` adds a light source to the projectile.

| Attribute | Value | Description |
|---|---|---|
| `r`, `g`, `b` | `40`, `190`, `255` | RGB values for the light color. |
| `radius` | `30` | The radius of the light emitted by the projectile. |

## Audio

The `AudioComponent` specifies the sound effects associated with the projectile.

| Attribute | Value | Description |
|---|---|---|
| `file` | `data/audio/Desktop/projectiles.bank` | Path to the audio bank containing projectile sounds. |
| `event_root` | `player_projectiles/bullet_light` | The root event name for player projectile sounds. |

## Velocity and Physics

The `VelocityComponent` (inherited from `base_projectile.xml`) influences the projectile's movement.

| Attribute | Value | Description |
|---|---|---|
| `gravity_y` | `200` | The strength of gravity affecting the projectile on the Y-axis. |
| `air_friction` | `1.7` | The amount of air resistance applied to the projectile. |
| `mass` | `0.04` | The mass of the projectile, affecting its interaction with physics. |