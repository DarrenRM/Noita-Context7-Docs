---
title: Bounce Spark Projectile
category: entities
---

# Bounce Spark Projectile

This document details the configuration for the "bounce_spark" projectile entity in Noita, designed for AI-assisted modding.

## Core Functionality

The `bounce_spark` projectile is a player-fired projectile characterized by its ability to bounce multiple times and its explosive death effect.

## Key Components and Attributes

### ProjectileComponent

This is the primary component defining the projectile's behavior.

| Attribute             | Value                                     | Description                                                                                                |
| :-------------------- | :---------------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `lob_min`, `lob_max`  | `0.5`, `0.7`                              | Controls the arc of the projectile.                                                                        |
| `speed_min`, `speed_max`| `200`, `300`                              | Sets the initial speed range of the projectile.                                                            |
| `friction`            | `1`                                       | How much the projectile's speed is reduced by air resistance.                                              |
| `direction_random_rad`| `0.40`                                    | Introduces randomness to the projectile's initial direction.                                               |
| `on_death_explode`    | `1`                                       | The projectile explodes upon death.                                                                        |
| `on_lifetime_out_explode`| `1`                                       | The projectile explodes when its lifetime expires.                                                         |
| `on_collision_die`    | `1`                                       | The projectile is destroyed upon collision.                                                                |
| `lifetime`            | `100`                                     | The base duration of the projectile before expiring.                                                       |
| `damage`              | `0.2`                                     | The damage dealt by the projectile upon impact (before explosion).                                         |
| `bounce_always`       | `1`                                       | The projectile will always attempt to bounce.                                                              |
| `bounces_left`        | `20`                                      | The maximum number of bounces the projectile can perform.                                                  |
| `bounce_energy`       | `0.5`                                     | The amount of velocity retained after each bounce (0.5 means 50% is kept).                                 |
| `lifetime_randomness` | `7`                                       | Adds randomness to the projectile's lifetime.                                                              |
| `knockback_force`     | `0.5`                                     | The force applied to entities when the projectile hits them.                                               |
| `physics_impulse_coeff`| `2000`                                    | Affects the impulse applied during physics interactions.                                                   |
| `muzzle_flash_file`   | `data/entities/particles/muzzle_flashes/muzzle_flash_magic_small.xml` | Specifies the particle effect for the muzzle flash when fired.                                             |
| `shoot_light_flash_radius`, `r`, `g`, `b` | `64`, `70`, `190`, `255` | Defines the radius and color of the light flash emitted when the projectile is shot.                       |

### `config_explosion` (within `ProjectileComponent`)

Defines the properties of the explosion that occurs upon the projectile's death.

| Attribute                 | Value                                     | Description                                                                                                |
| :------------------------ | :---------------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `damage`                  | `0`                                       | The damage dealt by the explosion itself.                                                                  |
| `camera_shake`            | `0`                                       | Disables camera shake from the explosion.                                                                  |
| `explosion_radius`        | `4`                                       | The radius of the explosion effect.                                                                        |
| `explosion_sprite`        | `data/particles/background_cleaner_explosion.xml` | The sprite used for the explosion visual.                                                                  |
| `hole_destroy_liquid`     | `1`                                       | The explosion will destroy liquids.                                                                        |
| `hole_enabled`            | `1`                                       | The explosion creates a hole in the environment.                                                           |
| `ray_energy`              | `400000`                                  | The energy of the explosion's destructive rays.                                                            |
| `physics_explosion_power.min`, `.max` | `0.05`, `0.1` | The minimum and maximum power of the physics-based explosion force.                                        |
| `shake_vegetation`        | `1`                                       | The explosion will shake vegetation.                                                                       |
| `material_sparks_enabled` | `1`                                       | Sparks will be generated from destroyed materials.                                                         |
| `stains_enabled`          | `1`                                       | The explosion leaves stains on surfaces.                                                                   |
| `stains_radius`           | `3`                                       | The radius of the stains left by the explosion.                                                            |

### SpriteComponent

Defines the visual appearance of the projectile.

| Attribute       | Value                                     | Description                                                                                                |
| :-------------- | :---------------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `image_file`    | `data/projectiles_gfx/background_cleaner.xml` | The sprite sheet or animation file for the projectile.                                                     |
| `rect_animation`| `fireball`                                | Specifies the name of the animation to use from the `image_file`.                                          |
| `emissive`      | `1`                                       | The sprite emits light.                                                                                    |
| `additive`      | `1`                                       | The sprite uses additive blending for its rendering.                                                       |

### SetStartVelocityComponent

Applies initial velocity variations to the projectile.

| Attribute             | Value                                     | Description                                                                                                |
| :-------------------- | :---------------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `randomize_speed.min`, `.max` | `40`, `160` | The range for randomizing the projectile's initial speed.                                                  |
| `randomize_angle.max` | `6.283185` (2π)                           | The maximum angle (in radians) for randomizing the projectile's initial direction.                         |

### AudioComponent

Handles the sound effects associated with the projectile.

| Attribute   | Value                                     | Description                                                                                                |
| :---------- | :---------------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank`     | The audio bank containing the sound events.                                                                |
| `event_root`| `player_projectiles/bullet_bubble`        | The root event name for the projectile's sounds.                                                           |

### LightComponent

Adds a light source to the projectile.

| Attribute     | Value                                     | Description                                                                                                |
| :------------ | :---------------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `radius`      | `60`                                      | The radius of the light emitted by the projectile.                                                         |
| `fade_out_time`| `0.1`                                     | How quickly the light fades out.                                                                           |
| `r`, `g`, `b` | `10`, `40`, `80`                          | The RGB color values of the emitted light.                                                                 |

### VariableStorageComponent

Stores custom variables for the entity.

| Attribute    | Value                                     | Description                                                                                                |
| :----------- | :---------------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `name`       | `projectile_file`                         | The name of the variable.                                                                                  |
| `value_string`| `data/entities/projectiles/deck/bounce_spark.xml` | The string value, typically pointing to the entity's own file path.                                        |