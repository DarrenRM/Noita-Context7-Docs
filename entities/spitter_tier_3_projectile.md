---
title: Spitter Tier 3 Projectile
category: entities
---

# Spitter Tier 3 Projectile

This document details the configuration for the "Spitter Tier 3" projectile in Noita, designed for AI-assisted modding.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior and characteristics of the projectile.

| Attribute             | Value      | Description                                                                 |
| :-------------------- | :--------- | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`  | `0.5`, `0.7` | Controls the arc of the projectile.                                         |
| `speed_min`, `speed_max` | `800`, `1000` | The initial velocity range of the projectile.                               |
| `friction`            | `1`        | How much the projectile's speed is reduced by air resistance.               |
| `on_death_explode`    | `1`        | The projectile explodes when its lifetime ends or it collides.              |
| `on_collision_die`    | `1`        | The projectile is destroyed upon collision.                                 |
| `lifetime`            | `35`       | The maximum duration of the projectile in frames before exploding.          |
| `damage`              | `0.6`      | The base damage dealt by the projectile.                                    |
| `bounce_always`       | `1`        | The projectile will always attempt to bounce.                               |
| `bounces_left`        | `10`       | The maximum number of bounces the projectile can perform.                   |
| `bounce_energy`       | `0.6`      | The energy retained after each bounce (0.0 to 1.0).                         |
| `bounce_fx_file`      | `...spitter_purple.xml` | Specifies the particle effect to spawn on bounce.                         |
| `knockback_force`     | `1.0`      | The force applied to entities upon collision.                               |
| `physics_impulse_coeff` | `1600`     | Coefficient for physics impulse applied on collision.                       |

### Explosion Configuration

The `config_explosion` sub-element within `ProjectileComponent` details the effects when the projectile explodes.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `damage`                  | `0.0`   | Damage dealt by the explosion itself (distinct from projectile damage).     |
| `camera_shake`            | `0`     | Intensity of camera shake on explosion.                                     |
| `explosion_radius`        | `2`     | The radius of the explosion effect.                                         |
| `ray_energy`              | `400000`| Energy of the explosion's raycast, affecting destruction.                   |
| `damage_mortals`          | `1`     | Whether the explosion damages living entities.                              |
| `physics_explosion_power` | `0`     | Minimum and maximum physics force applied by the explosion.                 |
| `shake_vegetation`        | `1`     | Whether the explosion shakes vegetation.                                    |
| `material_sparks_enabled` | `1`     | Enables sparks from destroyed materials.                                    |
| `stains_enabled`          | `1`     | Enables blood/liquid stains on surfaces.                                    |
| `stains_radius`           | `3`     | The radius of the stains created.                                           |

## Visual and Audio Components

### Sprite Component

The `SpriteComponent` defines the visual appearance of the projectile.

| Attribute      | Value                     | Description                                                                 |
| :------------- | :------------------------ | :-------------------------------------------------------------------------- |
| `image_file`   | `data/projectiles_gfx/spitter_purple.xml` | The sprite sheet or animation definition for the projectile.                |
| `rect_animation` | `fireball`                | Specifies the animation to use from the `image_file`.                       |
| `emissive`     | `1`                       | Makes the sprite emit light.                                                |
| `additive`     | `1`                       | Uses additive blending for the sprite, often for glowing effects.           |

### Audio Component

The `AudioComponent` handles the sound effects associated with the projectile.

| Attribute   | Value                     | Description                                                                 |
| :---------- | :------------------------ | :-------------------------------------------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank` | The Wwise bank containing the audio events.                                 |
| `event_root`| `player_projectiles/bullet_smg` | The root event path for player projectile sounds.                           |

### Light Component

The `LightComponent` adds a dynamic light source to the projectile.

| Attribute | Value | Description                                                                 |
| :-------- | :---- | :-------------------------------------------------------------------------- |
| `radius`  | `60`  | The radius of the light emitted by the projectile.                          |
| `r`, `g`, `b` | `40`, `10`, `80` | The RGB color values of the light.                                          |

## Particle Emitters

The projectile utilizes two `ParticleEmitterComponent`s to generate visual effects.

### Emitter 1 (Main Sparks)

| Attribute               | Value             | Description                                                                 |
| :---------------------- | :---------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name` | `spark_purple_bright` | The material used for the emitted particles.                                |
| `count_min`, `count_max`| `2`, `8`          | The range of particles emitted per interval.                                |
| `lifetime_min`, `lifetime_max` | `0.8`, `1.4`      | The duration of each emitted particle.                                      |
| `gravity.y`             | `20`              | The downward gravitational force applied to particles.                      |
| `fade_based_on_lifetime`| `1`               | Particles fade out as their lifetime decreases.                             |
| `is_emitting`           | `1`               | Enables the particle emitter.                                               |

### Emitter 2 (Secondary Sparks)

| Attribute               | Value             | Description                                                                 |
| :---------------------- | :---------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name` | `spark_purple_bright` | The material used for the emitted particles.                                |
| `count_min`, `count_max`| `1`, `4`          | The range of particles emitted per interval.                                |
| `gravity.y`             | `-10`             | The upward gravitational force applied to particles.                        |
| `lifetime_min`, `lifetime_max` | `0.55`, `1.4`     | The duration of each emitted particle.                                      |
| `airflow_force`         | `1.3`             | Force applied by airflow to particles.                                      |
| `airflow_time`          | `0.1`             | Duration of airflow effect on particles.                                    |
| `airflow_scale`         | `0.03`            | Scale of the airflow effect.                                                |
| `fade_based_on_lifetime`| `1`               | Particles fade out as their lifetime decreases.                             |
| `is_emitting`           | `1`               | Enables the particle emitter.                                               |

## Variable Storage

The `VariableStorageComponent` is used to store the projectile's own file path, likely for internal referencing.

| Attribute   | Value                                | Description                                                                 |
| :---------- | :----------------------------------- | :-------------------------------------------------------------------------- |
| `name`      | `projectile_file`                    | The name of the variable.                                                   |
| `value_string`| `data/entities/projectiles/deck/spitter_tier_3.xml` | The string value, which is the path to this entity's XML file.              |