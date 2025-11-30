---
title: Small Grenade Projectile
category: entities
---

# Small Grenade Projectile

This document details the configuration of the `grenade_small.xml` entity, representing a small grenade projectile in Noita.

## Core Components

### ProjectileComponent

This is the primary component defining the projectile's behavior.

| Attribute                 | Value                               | Description                                                                 |
| :------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`      | `0.9`, `1.0`                        | Controls the arc of the projectile. Higher values mean a flatter trajectory. |
| `speed_min`, `speed_max`  | `250`, `280`                        | The initial speed of the projectile.                                        |
| `friction`                | `0.6`                               | How much the projectile's speed is reduced over time due to air resistance. |
| `direction_random_rad`    | `0.05`                              | Adds a small random deviation to the projectile's initial direction.        |
| `on_death_explode`        | `1`                                 | The projectile explodes when it dies (e.g., after its lifetime ends).       |
| `on_lifetime_out_explode` | `1`                                 | Explicitly states explosion on lifetime expiry.                             |
| `on_collision_die`        | `1`                                 | The projectile is destroyed upon collision.                                 |
| `lifetime`                | `400`                               | The maximum duration (in frames) the projectile exists before expiring.     |
| `damage`                  | `0.7`                               | The base damage dealt by the projectile.                                    |
| `bounces_left`            | `4`                                 | The number of times the projectile can bounce off surfaces.                 |
| `knockback_force`         | `1.0`                               | The force applied to entities when hit by the projectile.                   |
| `friendly_fire`           | `1`                                 | Allows the projectile to damage the player who shot it.                     |

#### `damage_by_type`

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `fire`    | `0.3` | Additional fire damage applied.           |

#### `config_explosion`

Defines the properties of the explosion that occurs when the projectile dies.

| Attribute               | Value                                 | Description                                                                 |
| :---------------------- | :------------------------------------ | :-------------------------------------------------------------------------- |
| `camera_shake`          | `10`                                  | The intensity of camera shake during the explosion.                         |
| `explosion_radius`      | `12`                                  | The radius of the explosion's effect.                                       |
| `explosion_sprite`      | `data/particles/explosion_016.xml`    | The visual effect used for the explosion.                                   |
| `load_this_entity`      | `data/entities/particles/particle_explosion/main_gunpowder_tiny.xml` | The entity to load for the explosion's particle effects.                  |
| `hole_enabled`          | `1`                                   | Enables the creation of holes in terrain by the explosion.                  |
| `ray_energy`            | `350000`                              | The energy of the destructive rays emitted by the explosion.                |
| `damage`                | `0.5`                                 | The damage dealt by the explosion itself.                                   |
| `physics_explosion_power.min`, `physics_explosion_power.max` | `0.3`, `0.6` | The minimum and maximum force of the physics-based explosion.             |
| `shake_vegetation`      | `1`                                   | Causes the explosion to shake nearby vegetation.                            |
| `audio_event_name`      | `explosions/magic_grenade_tiny`       | The sound effect played during the explosion.                               |

### SpriteComponent

Defines the visual appearance of the projectile.

| Attribute    | Value                                | Description                               |
| :----------- | :----------------------------------- | :---------------------------------------- |
| `image_file` | `data/projectiles_gfx/grenade_scavenger_small.xml` | The sprite sheet or animation file.       |
| `offset_x`, `offset_y` | `4`, `4`                             | Adjusts the sprite's position.            |
| `additive`   | `1`                                  | Enables additive blending for the sprite. |

### ParticleEmitterComponent

Multiple emitters are used to create various visual effects.

*   **Smoke Emitter:**
    *   `emitted_material_name`: `smoke`
    *   `y_vel_min`, `y_vel_max`: `-5`, `0` (particles move upwards)
    *   `lifetime_min`, `lifetime_max`: `0.1`, `0.4`
*   **Fire Emitter:**
    *   `emitted_material_name`: `fire`
    *   `y_vel_min`, `y_vel_max`: `-5`, `0` (particles move upwards)
    *   `lifetime_min`, `lifetime_max`: `0.1`, `0.4`
*   **Spark Emitter (Initial Burst):**
    *   `emitted_material_name`: `spark`
    *   `x_vel_min`, `x_vel_max`: `-20`, `20`
    *   `y_vel_min`, `y_vel_max`: `-20`, `20`
    *   `lifetime_min`, `lifetime_max`: `0.1`, `0.3`
    *   `create_real_particles`: `0` (cosmetic)
    *   `gravity.y`: `300`
*   **Spark Emitter (Trail):**
    *   `emitted_material_name`: `spark`
    *   `gravity.y`: `-10` (particles move downwards slightly)
    *   `lifetime_min`, `lifetime_max`: `0.5`, `0.8`
    *   `airflow_force`: `1.2`
    *   `is_trail`: `1`
    *   `create_real_particles`: `0` (cosmetic)

### AudioComponent

*   `file`: `data/audio/Desktop/projectiles.bank`
*   `event_root`: `player_projectiles/bullet_launcher`

### LightComponent

*   `radius`: `60`
*   `r`, `g`, `b`: `120`, `80`, `10` (Warm orange light)

### VariableStorageComponent

*   `name`: `projectile_file`
*   `value_string`: `data/entities/projectiles/deck/grenade_small.xml` (Stores the entity's own file path)