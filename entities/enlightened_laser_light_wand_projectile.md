---
title: Enlightened Laser Light Wand Projectile
category: entities
---

# Enlightened Laser Light Wand Projectile

This document details the configuration of the "enlightened_laser_light_wand.xml" projectile entity in Noita, focusing on its key attributes for AI-assisted modding.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior and impact of the projectile.

### Key Attributes:

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `speed_min`               | `1`     | Minimum projectile speed.                                                   |
| `speed_max`               | `1`     | Maximum projectile speed.                                                   |
| `friction`                | `0.0`   | How much the projectile slows down over time.                               |
| `direction_random_rad`    | `0.05`  | Random deviation in projectile direction (in radians).                        |
| `lifetime`                | `52`    | Duration the projectile exists before expiring (in frames).                 |
| `damage`                  | `5`     | Base damage dealt by the projectile.                                        |
| `hit_particle_force_multiplier` | `5.5` | Multiplier for the force applied to particles upon collision.               |
| `camera_shake_when_shot`  | `3.0`   | Intensity of camera shake when the projectile is fired.                     |
| `shoot_light_flash_radius`| `80`    | Radius of the light flash effect when the projectile is fired.              |
| `knockback_force`         | `2.5`   | Force applied to entities that are hit by the projectile.                   |
| `collide_with_world`      | `0`     | Whether the projectile collides with the game world geometry.               |
| `penetrate_entities`      | `0`     | Whether the projectile can pass through other entities.                     |

## Scripting and Behavior

The `LuaComponent` links custom scripting to the projectile, enabling more complex behaviors.

### Key Attributes:

| Attribute           | Value                                             | Description                                                                 |
| :------------------ | :------------------------------------------------ | :-------------------------------------------------------------------------- |
| `script_source_file`| `data/scripts/projectiles/enlightened_laser_light.lua` | Path to the Lua script that controls the projectile's advanced logic.       |
| `execute_every_n_frame` | `50` | How often the Lua script's logic is executed (in frames).                   |
| `remove_after_executed` | `1` | Whether to remove the projectile after the script has executed once.        |

## Visual Effects (Particle Emitters)

Multiple `ParticleEmitterComponent` instances are used to create visual effects associated with the projectile.

### Image Emitters:

These emitters generate cosmetic particles that follow the projectile.

| Attribute                 | Value                               | Description                                                                 |
| :------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_white`, `spark_blue`         | The material used for the emitted particles.                                |
| `lifetime_min`, `lifetime_max` | `0.5` - `2`                         | Duration of individual particles.                                           |
| `count_min`, `count_max`  | `1` - `1`                           | Number of particles emitted per emission.                                   |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `1` - `1` | Interval between particle emissions.                                        |
| `direction_random_deg`    | `90`                                | Random spread of particle direction.                                        |
| `image_animation_file`    | `data/particles/image_emitters/wand_64.png` | Texture file for animated particles.                                        |
| `image_animation_speed`   | `10`                                | Speed of the particle animation.                                            |

### Launch Blast Emitters:

These emitters create visual effects at the moment the projectile is fired.

| Attribute                 | Value                               | Description                                                                 |
| :------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark_white`, `spark_blue`         | The material used for the emitted particles.                                |
| `delay_frames`            | `45` (blast a), `44` (blast circle) | Frames to wait before this emitter activates.                               |
| `offset.x`                | `27`                                | X-axis offset from the projectile's origin.                                 |
| `x_vel_min`, `x_vel_max`  | Varies                              | Minimum and maximum X velocity of emitted particles.                        |
| `y_vel_min`, `y_vel_max`  | Varies                              | Minimum and maximum Y velocity of emitted particles.                        |
| `velocity_always_away_from_center` | `1` | Particles are emitted outwards from the center.                             |
| `area_circle_radius.min`, `area_circle_radius.max` | Varies | Radius of the emission area.                                                |
| `friction`                | Varies                              | Friction applied to emitted particles.                                      |
| `count_min`, `count_max`  | Varies                              | Number of particles emitted per emission.                                   |
| `lifetime_min`, `lifetime_max` | Varies                              | Duration of individual particles.                                           |
| `emitter_lifetime_frames` | `3` (blast a), `2` (blast circle)   | How long the emitter itself is active.                                      |
| `emit_real_particles`     | `0`                                 | Whether to emit actual game entities or just cosmetic effects.              |

## Lighting

The `LightComponent` adds a light source to the projectile.

### Key Attributes:

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `radius`  | `100` | The radius of the light emitted by the projectile. |

## Audio

The `AudioComponent` defines the sound effects associated with the projectile.

### Key Attributes:

| Attribute     | Value                                   | Description                                                                 |
| :------------ | :-------------------------------------- | :-------------------------------------------------------------------------- |
| `file`        | `data/audio/Desktop/projectiles.bank`   | The audio bank containing the sound events.                                 |
| `event_root`  | `projectiles/enlightened_laser`         | The root event name for sounds related to this projectile.                  |

## Variable Storage

The `VariableStorageComponent` can store custom variables for use by other components or scripts.

### Key Attributes:

| Attribute    | Value                                           | Description                                                                 |
| :----------- | :---------------------------------------------- | :-------------------------------------------------------------------------- |
| `name`       | `projectile_file`                               | The name of the variable.                                                   |
| `value_string` | `data/entities/projectiles/enlightened_laser_light_wand.xml` | The string value stored, likely referencing its own file path.              |