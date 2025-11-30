---
title: Enlightened Laser Electric Wand Projectile
category: entities
---

# Enlightened Laser Electric Wand Projectile

This document details the configuration for the "Enlightened Laser Electric Wand" projectile in Noita, focusing on its core attributes and effects.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior of the projectile.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `speed_min`               | `1`     | Minimum projectile speed.                                                   |
| `speed_max`               | `1`     | Maximum projectile speed.                                                   |
| `friction`                | `0.0`   | Friction applied to the projectile.                                         |
| `direction_random_rad`    | `0.05`  | Randomness in projectile direction (in radians).                            |
| `lifetime`                | `82`    | Duration the projectile exists (in frames).                                 |
| `damage`                  | `5`     | Base damage dealt by the projectile.                                        |
| `knockback_force`         | `2.5`   | Force applied to knock back entities upon impact.                           |
| `camera_shake_when_shot`  | `3.0`   | Intensity of camera shake when the projectile is fired.                     |
| `shoot_light_flash_radius`| `80`    | Radius of the light flash emitted when the projectile is fired.             |
| `collide_with_world`      | `0`     | Whether the projectile collides with the environment.                       |
| `penetrate_entities`      | `0`     | Whether the projectile can pass through other entities.                     |

## Scripting and Logic

The `LuaComponent` links the projectile to custom scripting for advanced behavior.

| Attribute           | Value                                             | Description                                                                 |
| :------------------ | :------------------------------------------------ | :-------------------------------------------------------------------------- |
| `script_source_file`| `data/scripts/projectiles/enlightened_laser_elec.lua` | Path to the Lua script that controls the projectile's logic.                |
| `execute_every_n_frame`| `70`                                              | How often the Lua script logic is executed (in frames).                     |
| `remove_after_executed`| `1`                                               | Whether to remove the projectile after the script logic has executed.       |

## Visual Effects (Particle Emitters)

Several `ParticleEmitterComponent` instances are used to create visual flair.

### Image Emitter

This emitter generates cosmetic particles that trail the projectile.

| Attribute                     | Value                               | Description                                                                 |
| :---------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`       | `spark_blue`                        | The material used for the emitted particles.                                |
| `lifetime_min`                | `0.5`                               | Minimum lifetime of emitted particles.                                      |
| `lifetime_max`                | `2`                                 | Maximum lifetime of emitted particles.                                      |
| `count_min`                   | `1`                                 | Minimum number of particles emitted per burst.                              |
| `count_max`                   | `1`                                 | Maximum number of particles emitted per burst.                              |
| `emission_interval_min_frames`| `1`                                 | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames`| `1`                                 | Maximum frames between particle emissions.                                  |
| `direction_random_deg`        | `90`                                | Randomness in particle emission direction (in degrees).                     |
| `image_animation_file`        | `data/particles/image_emitters/wand_64.png` | Sprite sheet for animated particles.                                        |
| `image_animation_speed`       | `5`                                 | Speed of the particle animation.                                            |
| `image_animation_emission_probability` | `0.8`                               | Probability of emitting an animated particle.                               |

### Launch Blast A

This emitter creates a burst of sparks upon projectile launch.

| Attribute                     | Value                               | Description                                                                 |
| :---------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`       | `spark_blue`                        | The material used for the emitted particles.                                |
| `delay_frames`                | `65`                                | Delay in frames before this emitter activates.                              |
| `offset.x`                    | `27`                                | X-offset of the emitter origin.                                             |
| `x_vel_min`                   | `-20`                               | Minimum X velocity of emitted particles.                                    |
| `x_vel_max`                   | `800`                               | Maximum X velocity of emitted particles.                                    |
| `y_vel_min`                   | `-30`                               | Minimum Y velocity of emitted particles.                                    |
| `y_vel_max`                   | `30`                                | Maximum Y velocity of emitted particles.                                    |
| `area_circle_radius.min`      | `10`                                | Minimum radius of the emission area.                                        |
| `area_circle_radius.max`      | `10`                                | Maximum radius of the emission area.                                        |
| `count_min`                   | `30`                                | Minimum number of particles emitted per burst.                              |
| `count_max`                   | `50`                                | Maximum number of particles emitted per burst.                              |
| `lifetime_min`                | `0.1`                               | Minimum lifetime of emitted particles.                                      |
| `lifetime_max`                | `0.4`                               | Maximum lifetime of emitted particles.                                      |

### Launch Blast Circle

This emitter creates a circular burst of sparks upon projectile launch.

| Attribute                     | Value                               | Description                                                                 |
| :---------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`       | `spark_blue`                        | The material used for the emitted particles.                                |
| `delay_frames`                | `64`                                | Delay in frames before this emitter activates.                              |
| `offset.x`                    | `27`                                | X-offset of the emitter origin.                                             |
| `x_vel_min`                   | `0`                                 | Minimum X velocity of emitted particles.                                    |
| `x_vel_max`                   | `40`                                | Maximum X velocity of emitted particles.                                    |
| `y_vel_min`                   | `-5`                                | Minimum Y velocity of emitted particles.                                    |
| `y_vel_max`                   | `5`                                 | Maximum Y velocity of emitted particles.                                    |
| `area_circle_radius.min`      | `9`                                 | Minimum radius of the emission area.                                        |
| `area_circle_radius.max`      | `9`                                 | Maximum radius of the emission area.                                        |
| `count_min`                   | `30`                                | Minimum number of particles emitted per burst.                              |
| `count_max`                   | `60`                                | Maximum number of particles emitted per burst.                              |
| `lifetime_min`                | `0.2`                               | Minimum lifetime of emitted particles.                                      |
| `lifetime_max`                | `1.0`                               | Maximum lifetime of emitted particles.                                      |

## Lighting and Audio

| Component         | Details