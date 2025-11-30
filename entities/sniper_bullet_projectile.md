---
title: Sniper Bullet Projectile
category: entities
---

# Sniper Bullet Projectile

This document details the configuration of the `sniperbullet.xml` entity, which defines the behavior and appearance of a sniper bullet projectile in Noita.

## Core Components

### `Entity`

The root element for the sniper bullet.

### `Base`

Inherits base projectile properties from `data/entities/base_projectile.xml`.

#### `VelocityComponent`

Defines the physical movement characteristics of the projectile.

| Attribute      | Value   | Description                                     |
|----------------|---------|-------------------------------------------------|
| `gravity_y`    | `20`    | Downward acceleration due to gravity.           |
| `air_friction` | `-2.0`  | Resistance to movement in the air.              |
| `mass`         | `0.05`  | The mass of the projectile.                     |

### `ProjectileComponent`

This is the primary component that governs the projectile's behavior.

| Attribute                 | Value   | Description                                                                 |
|---------------------------|---------|-----------------------------------------------------------------------------|
| `friendly_fire`           | `1`     | Allows the projectile to damage friendly entities.                          |
| `lob_min`                 | `0.8`   | Minimum lob angle for projectile trajectory.                                |
| `lob_max`                 | `1.1`   | Maximum lob angle for projectile trajectory.                                |
| `speed_min`               | `1450`  | Minimum initial speed of the projectile.                                    |
| `speed_max`               | `1650`  | Maximum initial speed of the projectile.                                    |
| `damage_scaled_by_speed`  | `1`     | Damage dealt is influenced by the projectile's speed.                       |
| `direction_random_rad`    | `0.003` | Small random deviation in projectile direction.                             |
| `on_death_explode`        | `1`     | The projectile explodes upon death (e.g., collision or lifetime end).       |
| `on_lifetime_out_explode` | `1`     | The projectile explodes when its lifetime expires.                          |
| `on_collision_die`        | `1`     | The projectile is destroyed upon colliding with an entity.                  |
| `lifetime`                | `50`    | The duration in frames before the projectile expires.                       |
| `ground_penetration_coeff`| `2`     | How effectively the projectile penetrates the ground.                       |
| `camera_shake_when_shot`  | `2.0`   | Amount of camera shake experienced by the shooter when the projectile is fired. |
| `create_shell_casing`     | `1`     | Spawns a shell casing effect when fired.                                    |
| `bounces_left`            | `0`     | Number of bounces the projectile can perform.                               |
| `damage`                  | `1`     | Base damage of the projectile.                                              |
| `knockback_force`         | `4.0`   | The force applied to entities that are hit by the projectile.               |

#### `config_explosion`

Defines the properties of the explosion that occurs when `on_death_explode` or `on_lifetime_out_explode` is true.

| Attribute                 | Value   | Description                                                                 |
|---------------------------|---------|-----------------------------------------------------------------------------|
| `damage`                  | `0.4`   | Damage dealt by the explosion.                                              |
| `camera_shake`            | `0.5`   | Camera shake caused by the explosion.                                       |
| `explosion_radius`        | `3`     | The radius of the explosion effect.                                         |
| `hole_enabled`            | `1`     | Enables the creation of holes in surfaces from the explosion.               |
| `ray_energy`              | `800000`| Energy value for the explosion's destructive rays.                          |
| `max_durability_to_destroy`| `10`    | Maximum durability of objects that can be destroyed by the explosion.       |
| `physics_explosion_power` | `0.5-1.5`| Minimum and maximum power of the physics-based explosion force.             |
| `stains_enabled`          | `1`     | Enables the creation of impact stains from the explosion.                   |
| `stains_radius`           | `3`     | The radius of the impact stains.                                            |

### `SpriteComponent`

Determines the visual representation of the projectile.

| Attribute    | Value                               | Description                               |
|--------------|-------------------------------------|-------------------------------------------|
| `image_file` | `data/projectiles_gfx/bullet.xml` | The sprite sheet or animation file used.  |
| `emissive`   | `1`                                 | The sprite emits light.                   |
| `additive`   | `1`                                 | Uses additive blending for the sprite.    |

### `AudioComponent`

Handles the sound effects associated with the projectile.

| Attribute   | Value                               | Description                                     |
|-------------|-------------------------------------|-------------------------------------------------|
| `file`      | `data/audio/Desktop/projectiles.bank`| The audio bank containing the sound events.     |
| `event_root`| `projectiles/bullet_sniper_enemy`   | The root event name for firing sounds.          |

### `AudioLoopComponent`

Manages looping audio effects, such as pass-by sounds.

| Attribute   | Value                               | Description                                     |
|-------------|-------------------------------------|-------------------------------------------------|
| `file`      | `data/audio/Desktop/projectiles.bank`| The audio bank containing the sound events.     |
| `event_name`| `projectiles/sniper_bullet_passby`  | The name of the looping audio event.            |
| `auto_play` | `1`                                 | The audio loop starts automatically.            |

### `VariableStorageComponent`

Stores custom variables for the entity.

| Attribute    | Value                                | Description                                     |
|--------------|--------------------------------------|-------------------------------------------------|
| `name`       | `projectile_file`                    | The name of the variable.                       |
| `value_string`| `data/entities/projectiles/sniperbullet.xml` | The string value, referencing its own file. |