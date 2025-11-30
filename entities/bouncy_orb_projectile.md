---
title: Bouncy Orb Projectile
category: entities
---

# Bouncy Orb Projectile

This document details the configuration for the "Bouncy Orb" projectile in Noita, designed for AI-assisted modding.

## Core Attributes

The `ProjectileComponent` defines the primary behavior and characteristics of the bouncy orb.

| Attribute                 | Value                               | Description                                                                 |
| :------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`                | `1`                                 | Enables the component.                                                      |
| `lob_min`, `lob_max`      | `0.5`, `0.7`                        | Controls the arc of the projectile.                                         |
| `speed_min`, `speed_max`  | `400`, `500`                        | Sets the initial velocity range.                                            |
| `friction`                | `1`                                 | How much the projectile slows down over time.                               |
| `direction_random_rad`    | `0.01`                              | Small random deviation in projectile direction.                             |
| `on_death_explode`        | `1`                                 | The projectile explodes upon death.                                         |
| `on_collision_die`        | `1`                                 | The projectile dies upon colliding with something.                          |
| `lifetime`                | `750`                               | Maximum duration in frames before dying (if not exploded/collided).         |
| `damage`                  | `0.2`                               | Base damage dealt by the projectile.                                        |
| `damage_scaled_by_speed`  | `1`                                 | Damage is increased based on projectile speed.                              |
| `bounces_left`            | `5`                                 | The number of times the projectile can bounce before dying.                 |
| `bounce_fx_file`          | `data/entities/particles/bounce_effects/bouncy_orb.xml` | Specifies the particle effect to spawn on bounce.                           |
| `knockback_force`         | `1.6`                               | The force applied to entities upon impact.                                  |
| `physics_impulse_coeff`   | `2000`                              | Coefficient for physics impulse, affecting how it interacts with the world. |

## Visuals

The `SpriteComponent` handles the visual representation of the bouncy orb.

| Attribute     | Value                               | Description                               |
| :------------ | :---------------------------------- | :---------------------------------------- |
| `_enabled`    | `1`                                 | Enables the component.                    |
| `image_file`  | `data/projectiles_gfx/bouncy_orb.xml` | Path to the sprite texture.               |

## Particle Effects

Multiple `ParticleEmitterComponent` instances are used to create visual effects.

### Trail Particles (2 emitters)

These emitters create a continuous trail behind the projectile.

| Attribute             | Value      | Description                                      |
| :-------------------- | :--------- | :----------------------------------------------- |
| `emitted_material_name` | `plasma_fading` | The material used for the emitted particles.     |
| `gravity.y`           | `0`        | Particles are not affected by gravity.           |
| `x_vel_min`, `x_vel_max` | `16`, `16` | Constant horizontal velocity for trail particles. |
| `count_min`, `count_max` | `1`, `4`   | Number of particles emitted per interval.        |
| `lifetime_min`, `lifetime_max` | `0.4`, `0.8` | Duration of the trail particles.                 |
| `is_trail`            | `1`        | Indicates these are trail particles.             |
| `emit_cosmetic_particles` | `1`        | Emits cosmetic particles (visual only).          |

### Burst Particles (2 emitters)

These emitters create bursts of particles at specific intervals or upon certain events.

| Attribute             | Value      | Description                                      |
| :-------------------- | :--------- | :----------------------------------------------- |
| `emitted_material_name` | `plasma_fading` | The material used for the emitted particles.     |
| `gravity.y`           | `0.0`      | Particles are not affected by gravity.           |
| `count_min`, `count_max` | `1`, `1` or `1`, `2` | Number of particles emitted per interval.        |
| `lifetime_min`, `lifetime_max` | `1.4`, `3.5` or `0.6`, `0.8` | Duration of the burst particles.                 |
| `is_trail`            | `0`        | Indicates these are not trail particles.         |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `8`, `20` or `1`, `10` | Controls the timing of particle bursts.          |
| `emit_cosmetic_particles` | `1`        | Emits cosmetic particles (visual only).          |

## Explosion Configuration

The `config_explosion` element defines the properties of the explosion that occurs when the projectile dies.

| Attribute                 | Value      | Description                                                              |
| :------------------------ | :--------- | :----------------------------------------------------------------------- |
| `damage`                  | `0.0`      | Base damage of the explosion itself (often overridden by projectile damage). |
| `camera_shake`            | `0.5`      | Intensity of camera shake upon explosion.                                |
| `explosion_radius`        | `2`        | The radius of the explosion effect.                                      |
| `explosion_sprite`        | `data/particles/explosion_016_plasma.xml` | The sprite used for the explosion visual.                                |
| `ray_energy`              | `200000`   | Energy of any rays emitted by the explosion.                             |
| `max_durability_to_destroy` | `8`        | Maximum durability of objects that can be destroyed by the explosion.    |
| `physics_explosion_power.max` | `0.3`      | Maximum power of the physics-based explosion force.                      |
| `stains_enabled`          | `1`        | Enables the creation of stains on surfaces.                              |
| `stains_radius`           | `3`        | The radius of the stains created.                                        |

## Audio

The `AudioComponent` links sound effects to the projectile.

| Attribute   | Value                                     | Description                               |
| :---------- | :---------------------------------------- | :---------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank`     | The audio bank containing the sounds.     |
| `event_root`| `player_projectiles/bullet_bouncy_orb`    | The specific sound event for this projectile. |

## Lighting

The `LightComponent` adds a light source to the projectile.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `_enabled`| `1`   | Enables the light component.              |
| `r`, `g`, `b` | `40`, `240`, `255` | The RGB color of the light.               |
| `radius`  | `30`  | The radius of the light effect.           |

## Variable Storage

The `VariableStorageComponent` stores a reference to the projectile's own XML file.

| Attribute   | Value                                | Description                               |
| :---------- | :----------------------------------- | :---------------------------------------- |
| `name`      | `projectile_file`                    | The name of the variable.                 |
| `value_string`| `data/entities/projectiles/deck/bouncy_orb.xml` | The value of the variable (file path).    |