---
title: Spitter Projectile
category: entities
---

# Spitter Projectile

This document details the configuration of the "Spitter" projectile entity in Noita, primarily focusing on its behavior, visual, and audio properties for AI-assisted modding.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior of the spitter projectile.

### Key Attributes:

| Attribute             | Value        | Description                                                                 |
| :-------------------- | :----------- | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`  | `0.5`, `0.7` | Controls the minimum and maximum lob angle (vertical deviation) of the projectile. |
| `speed_min`, `speed_max` | `400`, `600` | Defines the range of initial speeds for the projectile.                     |
| `friction`            | `1`          | How much air resistance affects the projectile's speed.                     |
| `on_death_explode`    | `1`          | The projectile will explode upon death (e.g., hitting a surface or expiring). |
| `on_lifetime_out_explode` | `1`      | The projectile will explode when its lifetime expires.                      |
| `explosion_dont_damage_shooter` | `1` | The explosion caused by this projectile will not harm the player who fired it. |
| `on_collision_die`    | `1`          | The projectile will be destroyed upon colliding with something.             |
| `lifetime`            | `25`         | The maximum duration (in frames) the projectile exists before expiring.     |
| `damage`              | `0.3`        | The base damage dealt by the projectile.                                    |
| `bounce_always`       | `1`          | The projectile will always attempt to bounce off surfaces.                  |
| `bounces_left`        | `10`         | The maximum number of bounces the projectile can perform.                   |
| `bounce_energy`       | `0.5`        | The proportion of velocity retained after each bounce.                      |
| `bounce_fx_file`      | `...spitter.xml` | Specifies the particle effect to spawn when the projectile bounces.         |
| `lifetime_randomness` | `7`          | Adds a random variation to the projectile's lifetime.                       |
| `knockback_force`     | `1.0`        | The force applied to entities that are hit by the projectile.               |
| `physics_impulse_coeff` | `3500`     | Coefficient for physics impulse applied on collision.                       |

### Explosion Configuration (`config_explosion`):

| Attribute             | Value   | Description                                                                 |
| :-------------------- | :------ | :-------------------------------------------------------------------------- |
| `damage`              | `0.0`   | The damage dealt by the explosion itself (distinct from projectile damage). |
| `explosion_radius`    | `2`     | The radius of the explosion effect.                                         |
| `ray_energy`          | `400000`| The energy of the destructive rays emitted by the explosion.                |
| `damage_mortals`      | `1`     | The explosion will damage living entities.                                  |
| `shake_vegetation`    | `1`     | The explosion will affect and potentially destroy vegetation.               |
| `material_sparks_enabled` | `1` | Sparks will be generated from destroyed materials.                          |
| `stains_enabled`      | `1`     | Stains will be left on surfaces where the explosion occurs.                 |
| `stains_radius`       | `3`     | The radius of the stains left by the explosion.                             |

## Visuals

### Sprite Component:

| Attribute       | Value                 | Description                                                              |
| :-------------- | :-------------------- | :----------------------------------------------------------------------- |
| `image_file`    | `...spitter.xml`      | The sprite sheet or definition file for the projectile's visual.         |
| `rect_animation`| `fireball`            | Specifies the name of the animation to use from the `image_file`.      |
| `emissive`      | `1`                   | The sprite emits light.                                                  |
| `additive`      | `1`                   | The sprite uses additive blending, making it appear brighter.            |

### Light Component:

| Attribute     | Value | Description                                                              |
| :------------ | :---- | :----------------------------------------------------------------------- |
| `radius`      | `60`  | The radius of the light emitted by the projectile.                       |
| `fade_out_time`| `0.1` | How quickly the light fades out.                                         |
| `r`, `g`, `b` | `80`, `10`, `40` | The RGB color values of the emitted light.                               |

## Audio

### Audio Component:

| Attribute   | Value                               | Description                                                              |
| :---------- | :---------------------------------- | :----------------------------------------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank` | The audio bank containing the projectile's sound events.                 |
| `event_root`| `player_projectiles/bullet_smg`     | The root event path for the projectile's sounds.                         |

## Other Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`):

This component inherits general projectile properties.

#### Velocity Component:

| Attribute     | Value | Description                                                              |
| :------------ | :---- | :----------------------------------------------------------------------- |
| `gravity_y`   | `200` | The strength of gravity acting on the projectile along the Y-axis.       |
| `air_friction`| `2.7` | The amount of air resistance affecting the projectile's movement.        |
| `mass`        | `0.02`| The mass of the projectile, affecting its inertia and interactions.      |

### Variable Storage Component:

| Attribute    | Value                               | Description                                                              |
| :----------- | :---------------------------------- | :----------------------------------------------------------------------- |
| `name`       | `projectile_file`                   | The name of the variable storing the projectile's own file path.         |
| `value_string`| `data/entities/projectiles/deck/spitter.xml` | The actual file path of this projectile entity.                          |