---
title: Chainsaw Projectile
category: entities
---

# Chainsaw Projectile

This document details the configuration of the Chainsaw projectile entity in Noita, focusing on its behavior and effects when fired.

## Entity Definition

The core of the projectile is defined by the `<Entity>` tag, specifying its name and player-related tags.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
```

## Projectile Component

This is the primary component that governs the projectile's physical and behavioral attributes.

### Key Attributes:

| Attribute                 | Value      | Description                                                                 |
| :------------------------ | :--------- | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`      | `0.8`, `1.0` | Controls the minimum and maximum lobbing angle of the projectile.           |
| `speed_min`, `speed_max`  | `0`, `400` | Sets the range for the projectile's initial speed.                          |
| `friction`                | `3.0`      | Determines how quickly the projectile loses speed due to air resistance.    |
| `on_death_explode`        | `1`        | The projectile will explode upon death (e.g., collision, lifetime end).     |
| `on_death_gfx_leave_sprite` | `0`        | Does not leave a sprite behind when it dies.                                |
| `on_lifetime_out_explode` | `1`        | The projectile explodes when its lifetime expires.                          |
| `ground_collision_fx`     | `1`        | Enables visual effects upon colliding with the ground.                      |
| `explosion_dont_damage_shooter` | `1`        | The explosion will not harm the entity that fired the projectile.           |
| `on_collision_die`        | `1`        | The projectile is destroyed upon colliding with another entity.             |
| `lifetime`                | `1`        | The duration (in seconds) the projectile exists before expiring.            |
| `damage`                  | `0.0`      | Base damage dealt by the projectile. (Note: This is 0, damage likely comes from explosion). |
| `camera_shake_when_shot`  | `2.0`      | The intensity of camera shake when this projectile is fired.                |
| `collect_materials_to_shooter` | `1`        | The projectile collects materials it hits and returns them to the shooter.  |
| `collide_with_tag`        | `hittable` | The projectile will collide with entities tagged as "hittable".             |
| `shoot_light_flash_r/g/b` | `255/240/30` | RGB values for the light flash emitted when the projectile is shot.       |
| `shoot_light_flash_radius`| `32`       | The radius of the light flash.                                              |

### Explosion Configuration (`config_explosion`):

This nested tag defines the properties of the explosion that occurs when the projectile dies.

| Attribute                 | Value      | Description                                                                 |
| :------------------------ | :--------- | :-------------------------------------------------------------------------- |
| `never_cache`             | `1`        | Prevents the explosion from being cached, ensuring it's always generated.   |
| `camera_shake`            | `1.5`      | Intensity of camera shake caused by the explosion.                          |
| `explosion_radius`        | `3`        | The radius of the explosion's effect.                                       |
| `explosion_sprite`        | `...spark` | The sprite used for the explosion particles.                                |
| `hole_enabled`            | `1`        | Creates a hole in surfaces where the explosion occurs.                      |
| `damage`                  | `0`        | Base damage of the explosion. (Likely overridden by `ray_energy`).          |
| `ray_energy`              | `20000`    | The energy of the damaging rays emitted by the explosion.                   |
| `hole_image`              | `...hole.png` | The image used for the explosion hole.                                      |
| `physics_explosion_power` | `0.2-0.3`  | The force applied to physics objects by the explosion.                      |
| `shake_vegetation`        | `1`        | The explosion will shake nearby vegetation.                                 |
| `material_sparks_enabled` | `1`        | Enables sparks generated from materials hit by the explosion.               |
| `is_digger`               | `1`        | Indicates the explosion has digging properties.                             |
| `stains_enabled`          | `1`        | Enables blood/gore stains from the explosion.                               |

## Particle Emitter Component

This component controls the visual particles emitted by the projectile.

| Attribute                 | Value      | Description                                                                 |
| :------------------------ | :--------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `smoke`    | The material used for the emitted particles (smoke in this case).           |
| `count_min`, `count_max`  | `10`, `17` | The range for the number of particles emitted per burst.                    |
| `x_vel_min`, `x_vel_max`  | `-10`, `10`| The range for horizontal velocity of emitted particles.                     |
| `y_vel_min`, `y_vel_max`  | `-10`, `10`| The range for vertical velocity of emitted particles.                       |
| `lifetime_min`, `lifetime_max` | `0.1`, `0.3` | The duration particles exist.                                               |
| `is_emitting`             | `1`        | Enables the particle emitter.                                               |

## Audio Loop Component

This component handles the looping sound effect associated with the projectile.

| Attribute     | Value                               | Description                                     |
| :------------ | :---------------------------------- | :---------------------------------------------- |
| `file`        | `data/audio/Desktop/projectiles.bank` | The audio bank containing the sound event.      |
| `event_name`  | `player_projectiles/chainsaw/loop`  | The specific sound event to play.               |
| `auto_play`   | `1`                                 | The sound starts playing automatically.         |

## Variable Storage Component

This component stores a string variable, likely for internal referencing.

| Attribute   | Value                                | Description                                     |
| :---------- | :----------------------------------- | :---------------------------------------------- |
| `name`      | `projectile_file`                    | The name of the variable.                       |
| `value_string` | `data/entities/projectiles/deck/chainsaw.xml` | The string value stored, referencing its own file. |