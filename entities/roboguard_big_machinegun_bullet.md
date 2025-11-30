---
title: Roboguard Big Machinegun Bullet
category: entities
---

# Roboguard Big Machinegun Bullet

This document details the configuration for the "Roboguard Big Machinegun Bullet" projectile entity in Noita, focusing on key attributes relevant to AI-assisted modding.

## Base Projectile Configuration

The projectile inherits fundamental properties from `base_projectile.xml`.

### Velocity Component

| Attribute      | Value | Description                                     |
| :------------- | :---- | :---------------------------------------------- |
| `gravity_y`    | 120   | Downward acceleration due to gravity.           |
| `mass`         | 0.08  | The mass of the projectile.                     |
| `air_friction` | 0.3   | Resistance to movement in the air.              |

## Projectile Component

This component defines the core behavior and characteristics of the projectile.

### Key Attributes

| Attribute                   | Value   | Description                                                                 |
| :-------------------------- | :------ | :-------------------------------------------------------------------------- |
| `_enabled`                  | 1       | Enables the projectile component.                                           |
| `lob_min`, `lob_max`        | 0.8-1.0 | Controls the minimum and maximum "lob" or arc of the projectile.            |
| `speed_min`, `speed_max`    | 600-750 | The range of initial speeds for the projectile.                             |
| `friction`                  | 1       | Friction applied to the projectile over time.                               |
| `direction_random_rad`      | 0.05    | Introduces a small amount of randomness to the projectile's initial direction. |
| `on_death_explode`          | 1       | The projectile explodes upon death (e.g., collision or lifetime end).       |
| `on_lifetime_out_explode`   | 1       | The projectile explodes when its lifetime expires.                          |
| `on_collision_die`          | 1       | The projectile is destroyed upon collision with an entity.                  |
| `lifetime`                  | 30      | The base duration (in frames) the projectile exists before expiring.        |
| `lifetime_randomness`       | 7       | Adds randomness to the projectile's lifetime.                               |
| `damage`                    | 0.45    | The base damage dealt by the projectile.                                    |
| `knockback_force`           | 2.6     | The force applied to entities that are hit by the projectile.               |
| `camera_shake_when_shot`    | 0.1     | The intensity of camera shake when this projectile is fired.                |
| `muzzle_flash_file`         | `...`   | Path to the particle effect for the muzzle flash.                           |
| `shoot_light_flash_radius`  | 100     | The radius of the light flash emitted when the projectile is shot.          |

### Damage by Type

| Type  | Value | Description                               |
| :---- | :---- | :---------------------------------------- |
| `fire`| 0.2   | Additional damage multiplier for fire.    |

### Config Explosion

Defines the properties of the explosion that occurs when `on_death_explode` or `on_lifetime_out_explode` is true.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `damage`                  | 0       | Damage dealt by the explosion itself (distinct from projectile damage).     |
| `camera_shake`            | 2.0     | Intensity of camera shake caused by the explosion.                          |
| `explosion_radius`        | 6       | The radius of the explosion's effect.                                       |
| `explosion_sprite`        | `...`   | Path to the particle effect used for the explosion visual.                  |
| `hole_enabled`            | 1       | Enables the creation of holes in terrain by the explosion.                  |
| `ray_energy`              | 300000  | Energy value for raycasting effects of the explosion.                       |
| `physics_explosion_power` | 0.1-0.3 | Minimum and maximum power of the physics-based explosion force.             |
| `physics_throw_enabled`   | 1       | Enables physics-based throwing of objects by the explosion.                 |
| `sparks_enabled`          | 1       | Enables the emission of sparks from the explosion.                          |
| `material_sparks_enabled` | 1       | Enables the emission of material-specific sparks.                           |
| `stains_enabled`          | 1       | Enables the creation of impact stains on surfaces.                          |
| `stains_radius`           | 1       | The radius of the impact stains.                                            |
| `spark_material`          | `plasma_fading` | The material used for the sparks.                                           |

## Sprite Component

Defines the visual appearance of the projectile.

| Attribute      | Value                                   | Description                               |
| :------------- | :-------------------------------------- | :---------------------------------------- |
| `image_file`   | `data/projectiles_gfx/fireball_smaller_blue.xml` | Path to the sprite image file.            |
| `rect_animation` | `fireball`                              | The name of the rectangle animation to use. |
| `additive`     | 1                                       | Enables additive blending for the sprite. |

## Audio Component

Handles the sound effects associated with the projectile.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank` | Path to the audio bank file.              |
| `event_root`| `projectiles/laser`                 | The root event name for projectile sounds. |

## Particle Emitter Components

These components define the particle effects generated by the projectile.

### Emitter 1 (Trail Sparks)

| Attribute              | Value   | Description                                                              |
| :--------------------- | :------ | :----------------------------------------------------------------------- |
| `emitted_material_name`| `spark_blue` | The material of the particles being emitted.                             |
| `is_trail`             | 1       | Indicates that these particles form a trail.                             |
| `trail_gap`            | 0.6     | The spacing between particles in the trail.                              |
| `lifetime_min`, `max`  | 0.1-0.2 | The minimum and maximum lifetime of the emitted particles.               |
| `airflow_force`        | 10.5    | The force of airflow affecting the particles.                            |
| `create_real_particles`| 0       | Whether to create actual physics-simulated particles.                    |
| `emit_cosmetic_particles`| 1       | Whether to emit cosmetic particles (visual effects only).                |
| `emission_interval_min_frames`, `max` | 1-2 | The frame interval between particle emissions.                           |

### Emitter 2 (Explosion/Impact Sparks)

| Attribute              | Value   | Description                                                              |
| :--------------------- | :------ | :----------------------------------------------------------------------- |
| `emitted_material_name`| `plasma_fading` | The material of the particles being emitted.                             |
| `is_trail`             | 1       | Indicates that these particles form a trail.                             |
| `trail_gap`            | 1.2     | The spacing between particles in the trail.                              |
| `lifetime_min`, `max`  | 0.2-0.6 | The minimum and maximum lifetime of the emitted particles.               |
| `airflow_force`        | 1.5     | The force of airflow affecting the particles.                            |
| `x_vel_min`, `max`     | 20-80   | The range of horizontal velocity for emitted particles.                  |
| `create_real_particles`| 0       | Whether to create actual physics-simulated particles.                    |
| `emit_cosmetic_particles`| 1       | Whether to emit cosmetic particles (visual effects only).                |
| `emission_interval_min_frames`, `max` | 1-2 | The frame interval between particle emissions.                           |

## Light Component

Defines any light emitted by the projectile.

| Attribute | Value | Description             |
| :-------- | :---- | :---------------------- |
| `radius`  | 30    | The radius of the light. |

## Variable Storage Component

Stores custom variables for the entity.

| Attribute   | Value                                         | Description                                     |
| :---------- | :-------------------------------------------- | :---------------------------------------------- |
| `name`      | `projectile_file`                             | The name of the variable.                       |
| `value_string`| `data/entities/projectiles/machinegun_bullet_roboguard_big.xml` | The value of the variable, pointing to its own file. |