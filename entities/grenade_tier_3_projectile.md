---
title: Grenade Tier 3 Projectile
category: entities
---

# Grenade Tier 3 Projectile

This document details the configuration for the "Grenade Tier 3" projectile in Noita, focusing on attributes relevant for AI-assisted modding.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior and characteristics of the projectile.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `_enabled`                | `1`     | Enables the projectile component.                                           |
| `lob_min`, `lob_max`      | `0.9`, `1.0` | Controls the minimum and maximum lob angle, influencing trajectory.         |
| `speed_min`, `speed_max`  | `250`, `280` | Sets the range for the projectile's initial speed.                          |
| `friction`                | `0.6`   | Determines how quickly the projectile loses velocity due to air resistance. |
| `direction_random_rad`    | `0.05`  | Adds a small amount of randomness to the projectile's initial direction.    |
| `on_death_explode`        | `1`     | Triggers an explosion when the projectile dies (e.g., hits a surface).      |
| `on_lifetime_out_explode` | `1`     | Triggers an explosion when the projectile's lifetime expires.               |
| `on_collision_die`        | `1`     | The projectile dies upon collision with an entity.                          |
| `lifetime`                | `500`   | The base duration of the projectile in frames before expiring.              |
| `lifetime_randomness`     | `7`     | Adds randomness to the projectile's lifetime.                               |
| `damage`                  | `2.0`   | The base damage dealt by the projectile.                                    |
| `bounces_left`            | `7`     | The number of times the projectile can bounce before being destroyed.       |
| `knockback_force`         | `2.0`   | The force applied to entities when hit by the projectile.                   |

### Damage Types

The `damage_by_type` element allows for specific damage modifiers against different damage types.

| Type  | Value | Description                               |
| :---- | :---- | :---------------------------------------- |
| `fire`| `1.8` | Applies a 1.8x multiplier to fire damage. |

### Explosion Configuration

The `config_explosion` element details the properties of the explosion triggered by the projectile.

| Attribute               | Value      | Description                                                                 |
| :---------------------- | :--------- | :-------------------------------------------------------------------------- |
| `camera_shake`          | `20`       | The intensity of camera shake upon explosion.                               |
| `explosion_radius`      | `40`       | The radius of the explosion's damage and effect.                            |
| `explosion_sprite`      | `...`      | Path to the sprite used for the explosion visual.                           |
| `load_this_entity`      | `...`      | Path to an entity to spawn upon explosion (e.g., particle effects).         |
| `create_cell_probability` | `60`       | Probability (in %) of creating a new cell upon explosion.                   |
| `hole_enabled`          | `1`        | Enables the creation of holes in terrain by the explosion.                  |
| `ray_energy`            | `5200000`  | The energy of the explosion's damaging rays.                                |
| `damage`                | `2.9`      | The damage dealt by the explosion itself.                                   |
| `physics_explosion_power.min`, `.max` | `0.6`, `0.9` | The minimum and maximum power of the physics-based explosion effect.        |
| `physics_throw_enabled` | `1`        | Enables physics-based throwing of objects by the explosion.                 |
| `sparks_enabled`        | `1`        | Enables the spawning of sparks upon explosion.                              |
| `sparks_count_min`, `max` | `30`, `50` | The range for the number of sparks spawned.                                 |
| `spark_material`        | `spark_purple_bright` | The material type of the sparks.                                            |
| `stains_enabled`        | `1`        | Enables the creation of stains on surfaces from the explosion.              |
| `stains_radius`         | `18`       | The radius of the stains created.                                           |
| `audio_event_name`      | `explosions/magic_grenade_big` | The name of the audio event to play upon explosion.                     |

## Visuals

### Sprite Component

The `SpriteComponent` defines the visual appearance of the projectile.

| Attribute      | Value                                 | Description                               |
| :------------- | :------------------------------------ | :---------------------------------------- |
| `image_file`   | `data/projectiles_gfx/grenade_purple.xml` | Path to the sprite's image file.          |
| `offset_x`, `y`| `4`, `4`                              | Offset of the sprite from the entity's center. |
| `additive`     | `1`                                   | Enables additive blending for the sprite. |

### Light Component

The `LightComponent` adds a light source to the projectile.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `radius`  | `60`  | The radius of the light.                  |
| `r`, `g`, `b` | `80`, `40`, `120` | The RGB color values of the light.        |

## Particle Emitters

Multiple `ParticleEmitterComponent` elements are used to generate various visual effects.

### Smoke Emitter

| Attribute               | Value   | Description                               |
| :---------------------- | :------ | :---------------------------------------- |
| `emitted_material_name` | `smoke` | The material of the emitted particles.    |
| `y_vel_min`, `max`      | `-5`, `0` | Controls the vertical velocity of smoke.  |
| `lifetime_min`, `max`   | `0.1`, `0.4` | Duration of emitted smoke particles.      |

### Fire Emitter

| Attribute               | Value  | Description                               |
| :---------------------- | :----- | :---------------------------------------- |
| `emitted_material_name` | `fire` | The material of the emitted particles.    |
| `y_vel_min`, `max`      | `-5`, `0` | Controls the vertical velocity of fire.   |
| `lifetime_min`, `max`   | `0.1`, `0.4` | Duration of emitted fire particles.       |

### Bright Purple Spark Emitter (Burst)

| Attribute               | Value                 | Description                                     |
| :---------------------- | :-------------------- | :---------------------------------------------- |
| `emitted_material_name` | `spark_purple_bright` | The material of the emitted particles.          |
| `count_min`, `max`      | `8`, `15`             | Number of sparks emitted in a burst.            |
| `lifetime_min`, `max`   | `1.6`, `3.9`          | Duration of emitted sparks.                     |
| `gravity.y`             | `20`                  | Downward gravity applied to sparks.             |
| `fade_based_on_lifetime`| `1`                   | Sparks fade out as their lifetime decreases.    |
| `create_real_particles` | `0`                   | Particles are cosmetic, not physical entities.  |

### Bright Purple Spark Emitter (Trail)

| Attribute               | Value                 | Description                                     |
| :---------------------- | :-------------------- | :---------------------------------------------- |
| `emitted_material_name` | `spark_purple_bright` | The material of the emitted particles.          |
| `count_min`, `max`      | `1`, `4`              | Number of sparks emitted in a trail segment.    |
| `gravity.y`             | `-10`                 | Upward gravity applied to sparks.               |
| `lifetime_min`, `max`   | `0.5`, `2.8`          | Duration of emitted sparks.                     |
| `airflow_force`, `time`, `scale` | `1.3`, `0.1`, `0.03` | Parameters for airflow affecting sparks.        |
| `is_trail`              | `1`                   | Indicates this emitter creates a trail effect.  |
| `trail_gap`             | `0.1`                 | Spacing between trail particles.                |
| `create_real_particles` | `0`                   | Particles are cosmetic, not physical entities.  |

## Audio

### Audio Component

The `AudioComponent` defines the sound effects associated with the projectile.

| Attribute      | Value                               | Description                               |
| :------------- | :---------------------------------- | :---------------------------------------- |
| `file`         | `data/audio/Desktop/projectiles.bank` | Path to the audio bank file.              |
| `event_root`   | `player_projectiles/bullet_launcher`| The root event name for projectile sounds. |

## Variables

### Variable Storage Component

The `VariableStorageComponent` stores custom variables for the entity.

| Attribute   | Value                                  | Description                               |
| :---------- | :------------------------------------- | :---------------------------------------- |
| `name`      | `projectile_file`                      | The name of the variable.                 |
| `value_string`| `data/entities/projectiles/deck/grenade_tier_3.xml` | The string value, referencing its own file. |