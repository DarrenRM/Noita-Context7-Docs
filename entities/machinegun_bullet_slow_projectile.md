---
title: Machinegun Bullet (Slow) Projectile
category: entities
---

# Machinegun Bullet (Slow) Projectile

This document details the configuration for a slow-moving machinegun bullet projectile in Noita, intended for AI-assisted modding.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior and characteristics of the bullet.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `speed_min`               | `600`        | Minimum projectile speed.                                                   |
| `speed_max`               | `700`        | Maximum projectile speed.                                                   |
| `friction`                | `1.5`        | How quickly the projectile loses speed due to air resistance.               |
| `direction_random_rad`    | `0.06`       | Random deviation in projectile direction (in radians).                        |
| `lifetime`                | `30`         | Duration (in frames) before the projectile expires.                         |
| `damage`                  | `0.15`       | Base damage dealt by the projectile.                                        |
| `knockback_force`         | `0.45`       | Force applied to entities upon impact.                                      |
| `on_death_explode`        | `1`          | If the projectile explodes upon death (e.g., hitting a wall or expiring). |
| `on_collision_die`        | `1`          | If the projectile is destroyed upon colliding with an entity.               |
| `create_shell_casing`     | `1`          | Whether to spawn a shell casing graphic upon firing.                        |
| `camera_shake_when_shot`  | `2.0`        | Magnitude of camera shake when this projectile is fired.                    |
| `shoot_light_flash_radius`| `64`         | Radius of the light flash emitted when the projectile is shot.              |

## Explosion Configuration

When the projectile explodes (`on_death_explode` or `on_lifetime_out_explode` is enabled), the `config_explosion` element dictates the explosion's properties.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `damage`                  | `0.4`   | Damage dealt by the explosion.                                              |
| `camera_shake`            | `0.5`   | Magnitude of camera shake caused by the explosion.                          |
| `explosion_radius`        | `2`     | The radius of the explosion's effect.                                       |
| `explosion_sprite`        | `...`   | Path to the sprite used for the explosion visual.                           |
| `hole_enabled`            | `1`     | If the explosion should create a hole in surfaces.                          |
| `hole_image`              | `...`   | Path to the image used for the explosion hole.                              |
| `ray_energy`              | `400000`| Energy value for the explosion's raycast effects.                           |
| `physics_explosion_power` | `0.08-0.1`| Minimum and maximum force applied to physics objects by the explosion.      |
| `stains_enabled`          | `1`     | If the explosion should leave stains on surfaces.                           |
| `stains_radius`           | `3`     | The radius of the stains left by the explosion.                             |

## Visuals and Audio

### Sprite Component

| Attribute     | Value                               | Description                               |
| :------------ | :---------------------------------- | :---------------------------------------- |
| `image_file`  | `data/projectiles_gfx/bullet.xml` | Path to the projectile's visual sprite. |

### Audio Component

| Attribute   | Value                               | Description                                     |
| :---------- | :---------------------------------- | :---------------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank` | Path to the audio bank containing projectile sounds. |
| `event_root`| `projectiles/minigun`               | The root event name for projectile sounds.      |

## Variables

The `VariableStorageComponent` is used to store specific variables related to the entity.

| Name           | Value                                     | Description                               |
| :------------- | :---------------------------------------- | :---------------------------------------- |
| `projectile_file`| `data/entities/projectiles/machinegun_bullet_slow.xml` | Stores the entity's own file path.        |